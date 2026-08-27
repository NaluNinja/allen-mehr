# Specification — Marginal Analysis Model (Perfect Competition)

**Engagement:** perfect-competition · **Capability:** marginal-analysis
**Status:** draft — written before `model.xlsx` exists.

This document is the build order for the workbook. Anyone unfamiliar with the case should be
able to build the model from this file alone, without asking a question.

## Naming Conventions

All named ranges are lowercase with underscores. Per-crop values use `<crop>_crop_<attribute>`,
so every fact about one crop groups together and the crop is never ambiguous. The three crops are
`tomato_crop`, `carrot_crop`, `mesclun_crop` — spelled exactly this way everywhere.

No formula may reference a cell address. Logic is written against names only.

## 1. Inputs — The Named Contract

Nothing downstream may use a number that does not appear here. Where a value is *derived* from
another input, the model stores the formula, not the rounded result.

**Why derived and not typed:** a truncated decimal is not a harmless simplification. Rounding
0.8333 to 0.833 shifts season profit by $7 on a 60-bed farm; the same truncation compounds through
every multiplication and scales with the size of the operation. At commercial scale it produces
consistent, invisible error. Store the relationship, let the sheet carry the precision.

### Farm-level inputs

| Named range | Value | Unit | Derived from | Source |
|---|---|---|---|---|
| `season_weeks` | 36 | weeks | — | case README — scenario table |
| `beds_total` | 64 | beds | — | case README — scenario table |
| `fixed_costs` | 20,000 | $/season | — | case README — scenario table |

### Labor inputs

| Named range | Value | Unit | Derived from | Source |
|---|---|---|---|---|
| `farmer_salary` | 50,000 | $/season | — | case README — scenario table |
| `farmer_hrs_wk` | 40 | hrs/week | — | case README — scenario table |
| `farmer_field_pct` | 50% | share | — | case README — scenario table |
| `farmer_hrs_paid` | 1,440 | hrs/season | `farmer_hrs_wk * season_weeks` | derived |
| `farmer_hrs_field` | 720 | hrs/season | `farmer_hrs_paid * farmer_field_pct` | derived |
| `farmer_wage` | 34.7222 | $/hr | `farmer_salary / farmer_hrs_paid` | derived |
| `temp_salary` | 25,000 | $/season/worker | — | case README — scenario table |
| `temp_hrs_each` | 1,440 | hrs/worker | — | case README — scenario table |
| `temp_wage` | 17.3611 | $/hr | `temp_salary / temp_hrs_each` | derived |
| `temp_max` | 4 | workers | — | case README — scenario table |
| `temp_hrs_avail` | 5,760 | hrs/season | `temp_max * temp_hrs_each` | derived |

**The wage denominator is `farmer_hrs_paid` (1,440), not `farmer_hrs_field` (720).** The farmer is
paid for all 1,440 hours and spends half of them in the field; only the 720 field hours are charged
to crops. Check: `farmer_hrs_field * farmer_wage` = $25,000, exactly half her salary.

Temporary workers are 100% field, so all of their hours are chargeable. Fractional workers are
permitted, and the capacity limit is expressed in **workers** (`temp_max` = 4), not in hours.

`temp_hrs_each` is stated as a given 1,440, deliberately **not** derived from the farmer's schedule.
A temporary worker is a separate contract; if the farmer changed her weekly hours, theirs would not
follow. Deriving it would encode a dependency the farm does not actually have.

### Crop inputs

| Named range | Tomato | Carrot | Mesclun | Unit | Source |
|---|---|---|---|---|---|
| `<crop>_crop_price` | 8,800 | 2,094 | 2,700 | $/bed | case README — crop table |
| `<crop>_crop_fert` | 880 | 440 | 880 | $/bed | case README — crop table |
| `<crop>_crop_dim` | 10.00% | 2.50% | 1.25% | per bed | case README — crop table |
| `<crop>_crop_cap` | 20 | 20 | 30 | beds | case README — crop table |
| `<crop>_crop_hrswk` | 2.50 | derived | derived | hrs/week/bed | case README — crop table |

Labor per bed for carrots and mesclun is defined by the case as a ratio of tomatoes, and is stored
that way:

| Named range | Formula | Unit | Source |
|---|---|---|---|
| `carrot_crop_hrswk` | `tomato_crop_hrswk / 3` | hrs/week/bed | case README — "tomato ÷ 3" |
| `mesclun_crop_hrswk` | `tomato_crop_hrswk / 2` | hrs/week/bed | case README — "tomato ÷ 2" |

### Decision variables

| Named range | Unit | Notes |
|---|---|---|
| `tomato_crop_beds` | beds | integer, Solver-controlled |
| `carrot_crop_beds` | beds | integer, Solver-controlled |
| `mesclun_crop_beds` | beds | integer, Solver-controlled |

## 2. Structure

The workbook has five sheets.

| Sheet | Purpose |
|---|---|
| `README` | Conventions, Solver setup steps, and the cell color key. |
| `Inputs` | Every named range in Component 1. The only sheet containing typed numbers. |
| `MC Schedules` | One block per crop, one row per bed from 0 to that crop's cap: labor hours, total cost, marginal cost, AVC, ATC. |
| `Mix` | The three decision cells, the farm labor build-up, the P&L, and the constraint checks. Solver runs here. |
| `Charts` | Marginal cost against price, one chart per crop. |

### The MC Schedules sheet must be independent of the mix

Each crop's schedule answers a standalone question: *if this were the only crop grown, what would
the marginal cost of the q-th bed be?* Each row therefore takes its `q` from **its own row index**.

No formula on `MC Schedules` may reference `tomato_crop_beds`, `carrot_crop_beds`, or
`mesclun_crop_beds`. If it does, the schedules shift every time Solver moves the mix, the reported
standalone crossings are not standalone, and an empty mix divides by zero.

### Constraint checks

Pass/fail flags live on `Mix`, adjacent to the P&L, so feasibility and profit are readable in one
glance rather than assumed from Solver having run. Flags required: total beds ≤ `beds_total`, each
crop's beds ≤ its `_cap`, and temporary workers needed ≤ `temp_max`.

### Color key

Standard finance-modeling convention, stated on `README`:

| Color | Meaning |
|---|---|
| Blue | Input — a typed value, traceable to the Component 1 table |
| Black | Calculated — must contain a formula |

The convention is load-bearing for the audit: a black cell holding a typed number is a visible
violation of "calculated cells contain formulas," not something that has to be hunted for.

## 3. Calculation Logic

Written in named-range notation and in dependency order. No formula anywhere in the workbook may
reference a cell address.

### 3.1 The labor function

For any crop `c` and any bed count `q`:

```
LABOR_HRS(c, q) = q * c_crop_hrswk * season_weeks * (1 + c_crop_dim) ^ q
```

The exponential term is the diminishing-returns engine: each additional bed makes every bed of that
crop slightly more labor-hungry. This function is used in two independent places — the mix on
`Mix`, and the standalone schedules on `MC Schedules` — with different `q` arguments.

### 3.2 Farm labor build-up (`Mix`)

```
mix_hrs_tomato       = LABOR_HRS(tomato,  tomato_crop_beds)
mix_hrs_carrot       = LABOR_HRS(carrot,  carrot_crop_beds)
mix_hrs_mesclun      = LABOR_HRS(mesclun, mesclun_crop_beds)
mix_hrs_total        = mix_hrs_tomato + mix_hrs_carrot + mix_hrs_mesclun

perm_hrs_used        = MIN(mix_hrs_total, farmer_hrs_field)
temp_hrs_used        = mix_hrs_total - perm_hrs_used
temp_workers_needed  = temp_hrs_used / temp_hrs_each

labor_cost_total     = perm_hrs_used * farmer_wage + temp_hrs_used * temp_wage
labor_rate_blended   = labor_cost_total / mix_hrs_total
```

**The farmer's 720 field hours are consumed before any temporary hours.** The ordering is a stated
costing convention of the case, not an optimization the model performs.

### 3.3 Season P&L (`Mix`)

Per-crop labor is charged at the **blended** rate, not at the wage the hours actually cost:

```
c_revenue      = c_crop_beds * c_crop_price
c_fert_cost    = c_crop_beds * c_crop_fert
c_labor_cost   = mix_hrs_c * labor_rate_blended
c_contribution = c_revenue - c_fert_cost - c_labor_cost

revenue_total  = SUM of c_revenue
fert_total     = SUM of c_fert_cost
season_profit  = revenue_total - fert_total - labor_cost_total - fixed_costs
```

The perm/temp split is a farm-level fact, not a crop-level one — the farmer does not spend her
expensive hours on one crop and cheap temp hours on another. Charging each crop what its hours
"actually" cost would be a modeling error, not a refinement. Note that
`SUM of c_labor_cost = labor_cost_total` by construction; this is a useful internal check.

### 3.4 Standalone marginal-cost schedules (`MC Schedules`)

One block per crop, rows `q = 0` to `c_crop_cap`. Every `q` comes from the row itself.

```
sched_hrs(c,q)        = LABOR_HRS(c, q)
sched_perm_hrs(c,q)   = MIN(sched_hrs(c,q), farmer_hrs_field)
sched_temp_hrs(c,q)   = sched_hrs(c,q) - sched_perm_hrs(c,q)
sched_labor(c,q)      = sched_perm_hrs(c,q) * farmer_wage + sched_temp_hrs(c,q) * temp_wage
sched_fert(c,q)       = q * c_crop_fert

sched_vc(c,q)         = sched_labor(c,q) + sched_fert(c,q)
sched_tc(c,q)         = sched_vc(c,q) + fixed_costs
```

The schedule applies the same perm-hours-first rule as the farm, so it reports what the next bed
would cost *this* farm rather than a generic one.

```
MC(c,q)   = sched_vc(c,q) - sched_vc(c,q-1)        for q >= 1
AVC(c,q)  = sched_vc(c,q) / q                      for q >= 1
ATC(c,q)  = sched_tc(c,q) / q                      for q >= 1
```

Marginal cost is a **discrete difference**, not a derivative — beds are whole, so the cost of the
7th bed is a real quantity. Fixed costs cancel in the subtraction, so MC is identical whether taken
from `sched_vc` or `sched_tc`; it is taken from `sched_vc` to make that independence explicit.
`fixed_costs` enters `ATC` only.

**Row `q = 0`** holds `sched_hrs = 0` and `sched_vc = 0`, giving `MC(1)` its subtraction base.
`MC`, `AVC`, and `ATC` at `q = 0` are **blank — not zero, and not an error**. Division by zero at
this row would violate the "no error cells" criterion in Component 4.

### 3.5 Standalone P = MC crossing

For each crop, report the largest `q` at which `MC(c,q) <= c_crop_price`.

Marginal cost is **not assumed to rise monotonically**. If MC falls at any point in a schedule, the
bed number where it happens is recorded as an observation in the audit findings. Locating it is in
scope for this stage; explaining it is not.

## 4. Validation Rules

The workbook is accepted only if it passes every check below. These are fixed before any output
exists, so a result cannot be accepted by relaxing the test that caught it.

### 4.1 Hand-calculated labor anchors

Two points, not one. A builder that drops the exponent and writes a flat `(1 + dim)` still
reproduces `q = 1` exactly — the second anchor is what catches it.

| Check | Expression | Required | Flat-exponent bug returns |
|---|---|---|---|
| Tomato at q=1 | `1 * 2.50 * 36 * 1.10^1` | 99.0 hrs | 99.0 hrs (passes — useless alone) |
| Tomato at q=10 | `10 * 2.50 * 36 * 1.10^10` | 2,334.4 hrs | 990.0 hrs (fails — catches it) |

### 4.2 Published check figures

| Metric | Required | Tolerance |
|---|---|---|
| Optimal mix | tomato 10 · carrot 20 · mesclun 30 (60 beds) | exact |
| Season profit | $42,762 | within $1 |
| Standalone P ≈ MC crossings | tomato ~10 · carrot ~10 · mesclun ~6 | ±1 bed |

A profit outside the $1 band is a defect to be traced, not a rounding difference to be absorbed.

### 4.3 Structural checks

- No error cells anywhere in the workbook: no `#DIV/0!`, `#REF!`, `#VALUE!`, `#NAME?`.
- Every calculated (black) cell contains a formula. Typed values appear only in blue input cells.
- No formula references a cell address; all logic runs on named ranges.
- No formula on `MC Schedules` references `tomato_crop_beds`, `carrot_crop_beds`, or
  `mesclun_crop_beds`.
- All constraint flags pass at the reported optimum.
- `farmer_hrs_field * farmer_wage` = $25,000 — half the farmer's salary, confirming the wage
  denominator is 1,440 and not 720.
- `SUM of c_labor_cost` = `labor_cost_total` — confirms the blended allocation conserves dollars.

### 4.4 Solver runs

Solver is run twice: from a `0 / 0 / 0` start and from a `20 / 0 / 0` start. Both results are
recorded. If they disagree, the disagreement is reported as path-dependence; the worse run is not
discarded.

Configuration: GRG Nonlinear, objective `season_profit` maximized, changing cells the three
`*_crop_beds`, decisions constrained to integers, plus the constraints in Component 2.

### 4.5 Independent cross-check

Mid-model values — not only the final profit — are compared against the Farm Profit Lab reference
implementation. Two models agreeing on the answer while disagreeing on labor hours is a failure.

### 4.6 When a check fails

The **spec** is corrected and the workbook regenerated. The workbook is not patched by hand and no
clarification is given in chat: either would leave this document describing something other than
what was built.

## 5. Outputs

Everything below must be readable off the workbook without deriving it by hand.

### 5.1 Decision

The three bed counts and the total planted.

### 5.2 Season P&L

`revenue_total`, `fert_total`, `labor_cost_total`, `fixed_costs`, `season_profit`.

### 5.3 Labor build-up

`mix_hrs_total`, `perm_hrs_used`, `temp_hrs_used`, `temp_workers_needed`, `labor_rate_blended`.

### 5.4 Per crop

Beds, labor hours, revenue, fertilizer cost, allocated labor cost, contribution.

### 5.5 Constraint status

One row per constraint: the limit, the amount used, and whether it is **binding or slack**. For each
bed cap, also the **marginal profit of one additional bed** if the cap were relaxed by one.

This block exists because the Stage 1 brief made a specific claim about which constraints bind. The
model reports the status as a value; what the values mean is Stage 3's work, not this stage's.

### 5.6 Marginal-cost schedules

Per crop, `q = 0` to cap: labor hours, variable cost, MC, AVC, ATC. Plus the standalone P = MC
crossing, and the bed number of any point where MC **falls** rather than rises — recorded as a
location only.

### 5.7 Charts

Marginal cost against price, one per crop, exportable for `analysis/figures/` in Stage 3.

## Audit Findings

_(written after the workbook is built)_

---

_Specification drafted 2026-08-26. Every modeling decision recorded here — the derived-input rule,
the wage denominator, the temp-hours contract, the perm-first costing convention, the discrete MC
definition, and the tolerances — is mine. Claude prompted the decisions section by section,
transcribed the answers, and ran the gap-finding pass permitted by the stage instructions; it did
not supply the judgment. See [prompt-log.md](../../prompt-log.md)._

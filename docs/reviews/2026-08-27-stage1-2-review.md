<!-- PR TARGET: https://github.com/NaluNinja/allen-mehr | Stage 1.2 (8 pts) -->
# Stage 1.2 review — spec, build, audit

**Held — not entered. Spec-side: 62 of the 62.5 points available before a workbook exists.**

**Spec:** [`capabilities/marginal-analysis/spec.md`](https://github.com/NaluNinja/allen-mehr/blob/main/capabilities/marginal-analysis/spec.md)

> Graded early, at the instructor's request. Stage 1.2 is not due until 6 September and nothing was required yet. You have a specification and no workbook, which is exactly the right state to be in at this point — the stage is deliberately sequenced spec first. I am not entering a score, because 37.5 of the 100 points on this stage are for a workbook that does not exist yet and a number computed against those would say something false about the work. What follows is where the spec-side points stand and what to fix before you build.

| Criterion | Earned | Notes |
|---|---|---|
| Spec completeness — inputs, structure, calculation flow | 37 / 37.5 | Buildable from this file alone, which is what the opening line claims and the document delivers. Every input is named, unit-carried, and sourced, and — uniquely in this cohort — the table has a "Derived from" column, so a reader can see at a glance which numbers came from the case and which came from you. That distinction is the one thing the strongest completed workbook in this cohort still gets wrong. Three specific decisions are worth naming. You reasoned out the wage denominator — farmer_salary / 1,440 paid hours, not / 720 field hours — and then wrote a check that proves it: farmer_hrs_field x farmer_wage = $25,000, exactly half her salary. You declined to derive temp_hrs_each from the farmer's schedule, on the grounds that "a temporary worker is a separate contract; if the farmer changed her weekly hours, theirs would not follow. Deriving it would encode a dependency the farm does not actually have." That is modeling judgment, not bookkeeping. And you quantified the rounding rule rather than asserting it: rounding 0.8333 to 0.833 shifts season profit by about $7 on a 60-bed farm, and compounds with scale. I checked that figure and it is right. Half a point off for one omission: §4.4 constrains the decisions to integers and §2 lists the cap and total-bed flags, but non-negativity is never stated as a Solver constraint anywhere. |
| Spec validation rules | 25 / 25 | The best validation section in the cohort and the reason is §4.1. You specified two labor anchors rather than one, and you gave the reason in the table itself: "A builder that drops the exponent and writes a flat (1 + dim) still reproduces q = 1 exactly — the second anchor is what catches it." Then you wrote the column that makes it a test: tomato at q = 10 requires 2,334.4 hours, and the flat-exponent bug returns 990.0. That is precisely the defect sitting in one of the two completed workbooks in this cohort right now, identified in advance and given a tripwire. Both figures check out. §3.5 is the same quality of thinking: you worked out that marginal cost is not monotonic here, that "the largest q where MC <= price" therefore reads the wrong region of the schedule, and that the naive rule returns 20 and 30 against published values of about 10 and 6. You then wrote the correct definition — the largest q for which MC <= price holds for every j up to q — before seeing a single output. Add the two conservation identities (the wage-denominator check and SUM of c_labor_cost = labor_cost_total), the no-ROUND rule, the binding tolerance at 0.0001 rather than floating-point equality, and "if they disagree, the disagreement is reported as path-dependence; the worse run is not discarded," and there is nothing here I would add. |
| Workbook satisfies the contract | 0 / 25 | No workbook yet, and none was due. This is the part of the stage you have not reached, not a gap in the work. |
| Audit note | 0 / 12.5 | Correctly left as a stub for after the build. §4.6 already sets the policy that will make the audit honest — see below — so the hard part of this criterion is arguably done. |
| **Spec-side subtotal** | **62 / 62.5** | the part that can be earned before a workbook exists |

> Where this leaves you: 62 of 62.5 on the two spec criteria — the highest spec-side result in the cohort, including against the one completed workbook that reconciles to the cent. The remaining 37.5 become available once model.xlsx exists and you have audited it.

### The paragraph that matters most

§4.6: "The spec is corrected and the workbook regenerated. The workbook is not patched by hand and no clarification is given in chat: either would leave this document describing something other than what was built."

That is the whole discipline of this stage in three lines, and almost nobody writes it down. The reason it matters is not tidiness. A spec that drifts from the artifact is worse than no spec, because it is a document that reads as authoritative and is quietly false — and the drift always happens the same way, one urgent hand-fix at a time, each of which felt reasonable.

The "no clarification is given in chat" half is the sharper of the two. It is the part people violate without noticing, because answering a builder's question in conversation feels like helping rather than like amending the contract.

### The other thing worth naming

§5.5 requires the marginal profit of relaxing each bed cap, and specifies that it be produced by re-solving rather than read off the marginal-cost schedule: "Relaxing a cap lets the entire mix re-optimize, and the honest answer to 'what is one more bed worth' has to include that adjustment."

That is a shadow price correctly understood, and the distinction you are drawing is one that gets missed in professional work regularly. The schedule figure answers "what would the next bed of this crop cost in isolation." The re-solved figure answers the question anyone actually asked, which is "what is this constraint costing me." They are not the same number, and only the second one supports a recommendation.

The same section closes with a line that shows you know where the boundaries of this stage are: "The model reports the status as a value; what the values mean is Stage 3's work, not this stage's." Building the instrument now and refusing to interpret it yet is the right sequencing, and it is what will make Stage 3 straightforward.

### What I'd add, and it is short

- State non-negativity as a Solver constraint. Integrality is in §4.4 and the caps are in §2, but nothing in the document says beds cannot go below zero. GRG Nonlinear will not usually wander there given the objective, but "usually" is not a specification, and you are one line from closing it.

- Add the labor build-up to §4.2. Your acceptance table carries the mix, the profit, and the crossings. The case also publishes about 5,277 total labor hours and roughly 3.16 temporary workers at the optimum. Profit is a difference of large numbers, so two offsetting errors can land on the right total; the hours figure is much harder to hit by accident and it is the one that would fail loudly.

- Specify what the Farm Profit Lab cross-check compares. §4.5 says mid-model values rather than only the final profit, and the principle — "two models agreeing on the answer while disagreeing on labor hours is a failure" — is exactly right. Name two or three specific quantities and the bed counts to take them at, so the check has a definite pass condition rather than a good intention.

### What happens next

Build from this and audit it hard. Your spec has set the tests so well that the audit should mostly be a matter of running them and recording what happened — which is the position you want to be in, and it is the direct payoff for the work you did before opening Excel.

One caution, and it is the standard failure mode for a spec this good. When the workbook comes back and something disagrees with §4.2, the temptation is to decide the tolerance was too tight or the check figure was approximate. You have already written the answer to that — "a profit outside the $1 band is a defect to be traced, not a rounding difference to be absorbed" — and the whole value of having written it in advance is that it now applies to you.

Record at least three checks in the Audit Findings section, each naming what it would have caught, plus any defects found and what you did about them. That is 12.5 points and it is the criterion most people leave empty, because by the time a model works nobody wants to write down what was wrong with it.

---

### How to work this review

Treat this PR the way an analyst treats feedback from a senior reviewer — a review is a proposal to engage with, not a checklist to rubber-stamp.

1. **Read it yourself first.** Form your own view before you change anything. Disagreeing *with a documented reason* is a legitimate, senior response.
2. **Stress-test it with an LLM.** Paste this review and your spec into your assistant and ask it to (a) explain anything you are unsure of, and (b) argue the *other side* — where might the reviewer be wrong, and what would you give up by making each change.
3. **Then correct the spec, not the workbook.** This is the rule that makes the stage work: when a check fails, you fix the specification and regenerate, so the document keeps describing what was actually built.
4. **Close the loop.** Reply in this thread with what you changed and what you pushed back on, then commit and push.

*Nothing here is final. Stage 1.2 is not due until 6 September, and the stage is re-graded from scratch at the deadline.*

— Adam

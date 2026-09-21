---
template: spec
purpose: "Research plan for the individual research paper — data sources, analysis, figures, and success criteria, fixed before the research starts"
audience: student
fields_required: [scope, sources, analysis, figures, recommendation, success_criteria, boundaries]
courses: [BUS-620]
---

# Spec — Generic Drug Shortages

**Author:** Allen Mehr
**Date:** 2026-09-20
**Version:** 0.4 (draft — §§1, 2, 3, 5, 7 filled; §4 Figure 2 image export open; §6 open)
**Brief:** [`docs/briefs/research-brief.md`](../../docs/briefs/research-brief.md)
**Verification:** [`source-verification.md`](./source-verification.md)

---

## 1. Scope & Question

Should Medicare pay hospitals and physicians a reliability add-on for generic sterile injectables,
conditioned on the contract naming a qualified alternate manufacturer, and what does that premium
actually buy?

This paper defends the add-on. It isn't a survey of why shortages happen. The brief's three causes
are single-manufacturer markets, demand that doesn't respond to price, and procurement that rewards
the lowest bid. I use them as setup for the recommendation. The Hamilton Project's loans-plus-stockpile
package stays in scope as the alternative I'm rejecting, and why I reject it is part of the argument.

Amoxicillin and IV saline are out of scope. I'm narrowing to cisplatin and carboplatin, because one
plant failure and the rationing that followed are documented in a single traceable episode, and four
pages can't carry four drugs. This costs me the oral contrast case, so Figure 1 now argues at the
category level, injectable against oral, without a named oral drug. The paper's title will name only
the two drugs I cover.

## 2. Data Sources

<!-- One row per source. Name the specific series or figure you take from it, not just the outlet.
     Verified = confirmed in source-verification.md. Anything not yet verified cannot enter the
     paper until it is. -->

| Source | What I take from it | Verified? |
|---|---|---|
| ASPE, *Return on Investment of Generic Injectable Prescription Drugs* (Dec 2024), NBK611650 — Methods | Fixed cost of entry, generic injectables (E(CC)): low $5,921,504 / medium $9,164,082 / high $12,218,777. ASPE's own derivation from Eastern Research Group (2021), not a figure lifted from ERG's Table A-6. | Yes |
| ASPE ROI brief, NBK611650 — Methods | COGS as share of revenue: injectables 42%, orals 36% | Yes |
| ASPE ROI brief, NBK611650 — Methods | Discount rate: 8.82% | Yes |
| ASPE ROI brief, NBK611650 — Methods | All dollars normalized to January 2024 CPI | Yes |
| ASPE ROI brief, NBK611650 — Methods | Launch window: July 2018 – July 2021; sales data July 2018 – June 2024 | Yes |
| ASPE ROI brief, NBK611650 — Results | Months to break-even, injectables: 15 (low) / 25 (medium) / 36 (high); orals: 13 | Yes |
| ASPE ROI brief, NBK611650 — Results | ROI at 36 months, injectables: 42% / 17% / 0%; orals: 55% | Yes |
| ASPE ROI brief, NBK611650 — Results | Share net profitable at 36 months, injectables: 40% / 30% / 24%; orals: 41% | Yes |
| ASPE ROI brief, NBK611650 — Results | Sample: 447 generic injectable firm-drug products; 6 exceeded $100,000,000 in net profitability (orals: 25 of 1,243) | Yes |

<!-- Then: what you still need and do not have. The ASHP quarterly series is the known gap. -->

## 3. Analysis

I can't prove the premium adds capacity. What I can show is that it changes the manufacturer's
participation decision. So the analysis is a breakeven: the price uplift needed to cover the cost of
entering a generic sterile injectable market, compared against the dollar cost of shortages.

The breakeven measures the cost of entry, meaning what it takes to develop a generic and get it
approved. It does not measure the capital cost of building a plant. So it tests one thing, whether a
manufacturer would participate. It can't settle the premium against the Hamilton loans on cost of
capital, because the loans act on plant capex and I don't measure that.

COGS runs 42% of revenue for generic injectables, so contribution margin is 58%. A product clears its
entry cost when 0.58 × revenue >= E(CC). For a product with 36-month revenue R, the required price
uplift is u = E(CC)/R − 0.58. I report this as a curve, not a single number. The uplift depends on
where a product sits in the revenue distribution, and ASPE only publishes that distribution in
$100,000 increments.

The figure has three limits, and I'm stating them next to it. It's a first-order bound. It doesn't
discount within the 36-month window the way ASPE does at 8.82%. It treats the premium as pure margin,
with volume and per-unit COGS unchanged. And it assumes the manufacturer actually captures the uplift.
The add-on is paid to hospitals and physicians, so nothing guarantees that. That gap is why §5 amends
the policy, and it isn't a footnote to the arithmetic.

Two limits sit on the data rather than the arithmetic. ASPE's cohort is generics launched between July
2018 and July 2021, a stretch of heavy price erosion, and those are newly launched products — cisplatin
and carboplatin are decades old. ASPE names that older cohort as the shortage-prone one it did not
examine. ASPE also says it cannot link profitability to shortage risk, which is the step from low
margin to exit to shortage that my argument runs on. Both go in the paper.

Three course concepts do the work here. Fixed costs and barriers to entry explain why sterile capacity
doesn't show up on its own. Price-inelastic demand explains why a shortage appears as rationing and
not as a higher price. Market structure explains why one plant failing removes supply nobody else can
replace.

For §5 to hold, the analysis has to show that the uplift needed to make a sterile line viable is small
next to the dollar cost of the shortages it prevents. If it isn't, the recommendation fails and the
Hamilton loans look better by comparison. I accept that as the result that would change my answer.

## 4. Figures

<!-- One row per planned figure. Graphics are 10% of the rubric and the paper needs at least one
     labeled figure. Each figure needs a claim it supports — a figure that decorates is a figure
     that gets cut. -->

| # | Figure | Claim it supports | Data source | Built? |
|---|---|---|---|---|
| 1 | Median years in shortage, by drug type | Injectable shortages last nearly three times as long as oral ones, because sterile capacity is slow and expensive to stand up. That is why a multi-year volume commitment is what lets a manufacturer finance a line | ASPE 2018–2023 | Yes — [`analysis/figures/shortage-duration-by-drug-type.svg`](../../analysis/figures/shortage-duration-by-drug-type.svg) |
| 2 | Required price uplift by product revenue — three lines for the low, medium and high E(CC) scenarios, with the 70%-underwater mark shown | What the premium costs depends on how far down the revenue distribution it has to reach. A flat add-on that rescues the median product does nothing for the tail | ASPE ROI brief (E(CC), COGS 42%) | Spreadsheet built — [`analysis/required-uplift-u.xlsx`](../../analysis/required-uplift-u.xlsx). Image export for the paper still to do. |

<!-- A third figure is optional. The generic price-decline series would support pillar three, but
     the 10–15% figure is time-bounded (see source-verification.md) and three scattered points
     from a secondary source is not a series. It needs a real price index or it does not get built. -->

## 5. Recommendation

**The policy.** Medicare should pay hospitals and physicians a reliability add-on for multi-year,
meaningful-volume contracts with quality-vetted sterile-injectable manufacturers. The add-on applies
only when the contract also names a qualified alternate manufacturer as a contingency source.

**The strongest objection.** A premium locks in incumbents and gets administered by the same GPOs
that created the race to the bottom. It could end up protecting margins without adding any capacity.
The funding side, changes to Medicaid rebates, could also shift costs elsewhere in the system.

**My answer.** Paying nothing for reliability is also a price. It's just paid later, in rationed
chemo doses instead of a line item.

I chose the premium over the Hamilton loans because it goes after the cause. Generics lose money on
about half their products, so a subsidized plant still sells into a price that doesn't cover it. A
3+ year volume commitment is also what lets a manufacturer finance sterile capacity, so the premium
covers the fixed-cost problem indirectly. The loans become setup.

The condition answers lock-in. The premium only pays out when the contract includes a second
qualified source, it is tied to auditable outcomes like fill rate and FDA inspection record rather
than incumbency, and contracts are re-bid at term end.

**Why the amendment matters.** The add-on is paid to hospitals and physicians, but the decision to
participate belongs to the manufacturer. So the money enters at the provider and has to reach the
manufacturer through a contract nobody audits. Nothing in the draft says it will arrive. Requiring a
verified, performing alternate source, and tying payment to fill rate, links the provider's money to
something only a real manufacturer relationship can produce. That is the amendment's job. It fits
Wosińska and Frank's critique, which says the draft doesn't explicitly address reliability and that
its complexity carries compliance costs. The pass-through problem is my argument, though, not one
they make.

**What I defend.** The main objection to the Senate draft is that it doesn't actually buy reliability.
I defend an amended version that does, and I say so on page one so a reader who knows the Brookings
critique doesn't assume I missed it.

The amendment tightens the draft and doesn't add a new condition. The draft already ties payment to
contingency contracts with alternate manufacturers. I add teeth. The alternate has to be verified and
performing, not just named in a contract, and payment rides on auditable outcomes like fill rate and
inspection record. The drafters already accepted the principle. My argument is that they wrote it in a
form nobody can check.

Wosińska and Frank wrote both the Hamilton proposal and the Brookings critique, so I cite them as
interested parties. Their $2 billion isn't budget-neutral either. Cost can't disqualify my premium
while it stays a detail for theirs.

**The funding half.** The Senate Finance draft lets the Secretary reduce or waive Medicaid inflation
rebates for generics in shortage, and it bars participating hospitals from accepting 340B discounts on
those drugs. The rebate waiver raises 340B ceiling prices, so part of the cost lands on 340B hospitals.
I treat this as a funding cost and not a flaw in the premium itself. The draft names no offset, so my
recommendation adds a requirement that the Secretary keep Medicaid whole.

<!-- SETTLED 2026-09-20 against the May 2024 discussion draft; see source-verification.md. The
     standing caveat is that the draft is not enacted text, so any bill number in the paper gets
     checked against it first. -->

## 6. Success Criteria

<!-- What a finished paper has to do. Constraints from the assignment are fixed; the rest is yours.

     Fixed: four pages, title page, at least one labeled figure, bibliography on its own page,
     APA/MLA/Chicago, PDF to the LMS. Peer review is double-anonymous — no repo URL and no
     identifying information on the body pages.

     Rubric weights: content 20%, analysis 30%, recommendation 30%, writing 10%, graphics 10%.

     Add your own, the ones that are checkable: every number traced to a verified source, every
     figure introduced and interpreted in the text, the recommendation following from the analysis
     rather than sitting beside it. -->

- [ ] Footnote the ASPE appendix ROI discrepancy, quoting main-body figures only.
- [ ] 
- [ ] 

## 7. AI Boundaries

| Part of the paper | Who does it | What AI does | How I check |
|---|---|---|---|
| Policy choice (§1) | Me | Laid out the options and the counterarguments. Drafted a paragraph covering what is in and out of scope. | I decided the choice. I rewrote both paragraphs in my own words and changed anything I did not agree with. |
| Sources (§2) | Me | Claude fetched the sources online and cross-referenced them. It then transcribed the figures I had verified. | I checked every ASPE figure line by line before it went in. |
| Breakeven (§3) | Me. I built the spreadsheet from the formula and ASPE's inputs. | Drafted the surrounding text. Produced the same table independently from the same formula and inputs. | I compared the two row by row (75 cells) and they agreed. Because we used the same formula and the same inputs, this catches arithmetic and transcription errors only. It does not check the formula or the inputs themselves. |
| Figures (§4) | Figure 2 is mine. | Built Figure 1 from ASPE's data and drafted the claim text for me to review. | I looked at each figure and confirmed, line by line, the values against the original source. |
| Recommendation (§5) | Me | Drafted the pass-through paragraph and the argument notes. | I rewrote them in my own words and own the argument. |
| Disclosure | Me | Drafted this table. | I rewrote it in my own words and checked every line against the prompt log. |

---

_§7's table and the row 20 log entry were drafted by Claude (Cowork) on 2026-09-20 from my direction,
and I've rewritten both. Claude (Cowork) also wrote replacement text for eight marked passages, which
I rewrote. Claude Code's earlier wording now survives only in comments, not in the paper's prose. §6 is
still mine to write. See [prompt-log.md](../../prompt-log.md)._

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
**Version:** 0.2 (draft — §§1, 3, 5 filled; §§2, 4, 6, 7 open)
**Brief:** [`docs/briefs/research-brief.md`](../../docs/briefs/research-brief.md)
**Verification:** [`source-verification.md`](./source-verification.md)

---

## 1. Scope & Question

Should Medicare pay hospitals and physicians a reliability add-on for generic sterile injectables,
conditioned on the contract naming a qualified alternate manufacturer, and what does that premium
actually buy?

The paper defends the add-on. It is not a survey of shortage causes: the brief's three pillars —
single-manufacturer market structure, price-inelastic hospital demand, and procurement that rewards
the lowest bid — are setup for the recommendation, not the subject. The Hamilton Project
loans-plus-stockpile package stays in scope as the alternative I reject, and the reason I reject it
is part of the argument.

Out of scope: amoxicillin and IV saline. The paper narrows to cisplatin and carboplatin, where the
single-plant failure and the rationing it caused are documented in one traceable episode. Four pages
does not hold four drugs.

<!-- Claude's wording from your "cut amoxicillin and saline" — rewrite in your voice.
     Two knock-ons to decide: (a) amoxicillin was the oral contrast case that gave Figure 1's
     oral bar a named example, so the figure now argues at category level only; (b) the brief's
     title names all four drugs, so the paper's title should not. -->

## 2. Data Sources

<!-- One row per source. Name the specific series or figure you take from it, not just the outlet.
     Verified = confirmed in source-verification.md. Anything not yet verified cannot enter the
     paper until it is. -->

| Source | What I take from it | Verified? |
|---|---|---|
| | | |

<!-- Then: what you still need and do not have. The ASHP quarterly series is the known gap. -->

## 3. Analysis

I can't prove the premium adds capacity. What I can show is that it changes the manufacturer's
participation decision. So the analysis is a breakeven: the price uplift needed to cover the cost of
entering a generic sterile injectable market, compared against the dollar cost of shortages.

The breakeven measures cost of entry — developing a generic and getting it approved — not the capital
cost of building a plant. It therefore tests the participation decision and nothing more. It does not
settle the capital-cost side against the Hamilton loans, because the loans act on plant capex and
this analysis does not measure plant capex.

The course concepts doing the work are fixed costs and barriers to entry (why sterile capacity does
not appear on its own), price-inelastic demand (why the shortage shows up as rationing rather than
as a higher price), and market structure (why a single plant failing removes supply nobody can
replace).

What the analysis has to show for §5 to hold: that the uplift required to make a sterile line
viable is small relative to the dollar cost of the shortages it prevents. If it is not, the
recommendation fails and the Hamilton loans look better by comparison. I accept that as the
condition that would make this come out the other way (2026-09-20).

<!-- STILL YOURS: four inputs, none of them sourced yet. If any one is not findable, better to
     know before building the analysis around it.
       - annuitized capital cost of an FDA-approved sterile injectable line
       - plant utilization / volume assumption
       - current net price per unit
       - cost of shortages on the other side of the comparison
     Shortage cost is dollar-costed (substitution, labor, wastage), decided 2026-09-20, so the
     comparison sits on one axis. Rationed doses stay in the paper as the thing the dollars stand
     in for, not as a second number.

     SOURCING STATUS as of 2026-09-20 (Claude Code search; none of this is verified yet):

     SHORTAGE COST — in reach.
       Vizient, "Beyond the Shortage: The Hidden Cost of Drug Supply Chain Disruptions" (2025):
       ~20 million hours spent managing shortages in 2023, ~$894M/yr in labor, up from just under
       $360M in 2019. Mayo Clinic Proceedings (2014): ~$216M annualized personnel cost — gives a
       decade-long trend line.
       TWO LIMITS: both are LABOR ONLY, so they exclude the substitution and wastage you said you
       would count, and both cover ALL shortages, not sterile injectables alone. Cited as-is they
       understate one side of your breakeven. Say so rather than letting it pass.

     CAPEX — not in reach at the right grain. Only company announcements, which are not cost
     accounting and mix branded and biologic work into the figure:
       Civica Rx $124.5M / 140,000 sq ft (Petersburg VA); Pfizer ~$500M (Michigan);
       Grand River Aseptic $60M / 61,500 sq ft (2020); CordenPharma EUR 80M (facility + lines).

     >>> RETRIEVED AND READ 2026-09-20. ASPE, "An Examination of the Return on Investment of
     Generic Injectable Prescription Drugs" (Dec 2024), NCBI Bookshelf NBK611650. HHS has already
     run this breakeven. Data: IQVIA National Sales Perspective, all generic injectable and oral
     products launched after June 2018 with at least 36 months of post-entry data.

       Months to financial break-even after market entry, generic INJECTABLES:
         15 (low fixed cost) / 25 (medium) / 36 (high).   Generic ORALS: 13.
       ROI at 36 months post launch, INJECTABLES: 42% (low) / 17% (medium) / 0% (high).
         ORALS: 55%.
       Share of firm-drug entries net profitable at 36 months, INJECTABLES:
         40% (low) / 30% (medium) / 24% (high).   ORALS: 41%.
       ASPE's own words: "even 36 months post firm-drug entry, the majority of generic injectable
       drugs are financially underwater."
       Also: a small subset of entries earns a disproportionate share of revenue, so the AVERAGE
       overstates what the MARGINAL entrant can expect. Work from the full distribution across all
       three fixed-cost scenarios, not from the mean, and not from any single scenario.

     THE HORIZON ROUGHLY LINES UP WITH THE CONTRACT TERM. ASPE's 36-month window is close to the
     Senate draft's three-year minimum. Across the fixed-cost scenarios, an injectable entrant is
     anywhere from comfortably ahead to barely returning anything by the time that term is up, and
     in every scenario most individual products are still underwater. The term by itself therefore
     does not pay; the PREMIUM has to. That is the quantitative form of the argument §5 already
     makes in words. Note the limits: 36 months is where ASPE's SAMPLE ENDS, not a derived
     horizon, and the scenarios are assumptions about fixed cost, not measurements of it.

     ALSO: the brief says generics "lose money on roughly half" their products. ASPE puts 60-76%
     of generic injectable entries underwater at 36 months. Your own source is stronger than your
     claim — and specific to injectables. Consider upgrading the sentence.

     >>> WHAT "FIXED COST" MEANS HERE — CHECK §3'S WORDING. ASPE's fixed cost scenarios come from
     Eastern Research Group (2021), "Cost of Generic Drugs" (ASPE/ERG, aspe.hhs.gov). ERG models
     the cost of DEVELOPING AND GETTING APPROVAL FOR a generic (ANDA) — fifteen development
     stages, 8.82% opportunity cost of capital, eighteen product-pathway models including
     injectable solutions. It does NOT model the capital cost of building a sterile line.
     §3 currently says "annualized sterile line," which is plant capex. These are different
     things and only one of them is sourceable.

     WHAT THE BREAKEVEN CAN AND CANNOT SETTLE. ERG's numbers are about getting a drug approved,
     not about building a plant. So this breakeven tests one thing: whether a manufacturer would
     ENTER. It does not adjudicate the premium against the Hamilton loans on the cost of capital,
     because the loans act on plant capex and nothing here measures plant capex. Say that in the
     paper rather than letting the comparison imply more than the analysis supports.

     RECOMMEND REFRAMING §3 to cost of ENTRY rather than plant capex, because that is the
     participation decision you said the analysis is about, and ERG states the rule as an
     equation: a generic applicant whose expected capitalized cost of development E(CC) is
     $6.5M "will enter a given market, if the expected present value of revenues over the
     lifetime of its generic, E(R), is $6.5 million or greater." E(R) >= E(CC) is your breakeven.
     The premium raises E(R). ($6.5M is ERG's SIMPLE ORAL example — $2.6M cash outlay
     capitalized for failures and 8.82% cost of capital.) DECIDED 2026-09-20: entry cost.

     >>> THE INJECTABLE ENTRY COST, FOUND 2026-09-20. Not in ERG Table A-6 — that table's eighteen
     models are small molecule, topical, NTI, inhalers, liposomes/dendrimers/polymeric micelles,
     iron carbohydrate complexes, ophthalmic emulsions and glatiramoids. There is no plain sterile
     injectable among them. ASPE derived its own figures from ERG's estimates instead, and states
     them in the ROI brief:

       Fixed cost of entry, generic injectables:
         low $5,921,504 / medium $9,164,082 / high $12,218,777   (ASPE, from ERG 2021)
       COGS as a share of revenue: injectables 42%, orals 36%   (Positano et al. 2019)
       Sample: 447 generic injectable firm-drug products.
       Distribution: right-skewed. 6 of the 447 cleared $100,000,000 in net profitability, which
       is what drags the average up. This is why the mean is the wrong statistic here.

     That is E(CC) for your E(R) >= E(CC) breakeven, in three scenarios, with a variable-cost share
     to go with it. WHAT IS STILL MISSING IS THE PREMIUM. We have the cost side and the shape of
     the revenue side; §3 still has to say what uplift closes the gap. That calculation has not
     been run. (Correcting my own "the inputs are complete" of 2026-09-20 — having E(CC) is not
     having the analysis.)

     SAMPLE AND UNITS, for the paper: products launched July 2018 – July 2021, sales data
     July 2018 – June 2024, all dollars normalized to January 2024 CPI, discount rate 8.82%.
     Say the launch window out loud — it is a stretch of heavy generic price erosion, so it is
     not a neutral period to draw a profitability sample from.

     >>> THE LIMIT THAT MATTERS MOST. ASPE's cohort is NEWLY LAUNCHED generics. Cisplatin and
     carboplatin are decades-old ones. ASPE says so itself: older generics are "frequently
     highlighted as being especially prone to shortage risk due to low profitability. Since our
     work focuses on newer generics, future work may expand to examine this older cohort." So the
     analysis describes entrants into the injectable market, not the drugs this paper is about.
     The bias probably runs your way — old off-patent injectables are unlikely to be MORE
     profitable than new launches — but that is an argument to make, not an assumption to lean on.
     ASPE also states it cannot "definitively link specific levels of profitability with shortage
     risks," which is exactly the causal step from low margin to exit to shortage. State both.

     >>> ON THE APPENDIX CONTRADICTION (settled 2026-09-20). Cite the main body: 42% low / 17%
     medium / 0% high. Higher fixed cost must mean lower ROI, and the break-even timings
     (15/25/36 months) rise with fixed cost in step with the main body. The appendix has ROI
     rising with fixed cost, which cannot be right. It is not a clean swap either — each figure is
     off by one (-1/0, 16/17, 41/42), so it reads like an earlier version or a rounding pass with
     the labels reversed. If the discrepancy is mentioned at all, it goes in a footnote, and the
     appendix numbers are not quoted.

     ALSO WORTH READING: Wosińska's written testimony to the Senate Finance Committee, 5 Dec 2023
     (brookings.edu/wp-content/uploads/2023/12/Senate-Finance-Testimony-Final-12.5.2023.pdf).
     She testified to the committee whose draft you defend, so it bears on §5 as well as §3.

     HAMILTON: checked. The page carries $2B with no sizing, and partial loan forgiveness tied to
     quality milestones. The full PDF would not parse here. My earlier claim that it "probably
     contains the capital cost figures" was overstated — treat it as unconfirmed. -->

## 4. Figures

<!-- One row per planned figure. Graphics are 10% of the rubric and the paper needs at least one
     labeled figure. Each figure needs a claim it supports — a figure that decorates is a figure
     that gets cut. -->

| # | Figure | Claim it supports | Data source | Built? |
|---|---|---|---|---|
| 1 | Median years in shortage, by drug type | Sterile capacity is slow and costly to stand up, so injectable shortages run 2.89× oral ones — which is why a multi-year volume commitment is what finances a line | ASPE 2018–2023 | Yes — [`analysis/figures/shortage-duration-by-drug-type.svg`](../../analysis/figures/shortage-duration-by-drug-type.svg) |
| 2 | Breakeven: price uplift vs. annuitized line cost | The uplift needed is small relative to the shortage cost it prevents | §3 inputs, not yet sourced | No |

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

<!-- Claude's, 2026-09-20 — argument scaffolding, not your prose. Rewrite or cut.

     WHAT THE PAPER DEFENDS, STATED ON PAGE ONE. The leading objection to the Senate draft is
     that it does not actually buy reliability. The paper defends an amended version that does.
     Say this early or a reviewer meets the Brookings critique first and assumes it was missed.

     THE AMENDMENT IS A TIGHTENING, NOT AN INVENTION. This is the load-bearing point. The draft
     ALREADY conditions payment on contingency contracts with alternate manufacturers — that came
     out of your own 2026-09-20 bill check. So the amendment does not add the condition and must
     not be described as doing so. What it adds is teeth: the alternate must be verified and
     performing rather than merely named in a contract, and payment rides on auditable outcomes
     (fill rate, inspection record) instead of the draft's process measures and lump-sum payments.
     That is a far easier position to defend than proposing a new condition, because the drafters
     already conceded the principle — the argument is that they wrote it in a form that cannot be
     checked, which is precisely why Wosińska and Frank can say the program does not buy
     reliability.

     ON THE CRITICS. Wosińska and Frank wrote both the Hamilton loans-plus-stockpile proposal and
     the Brookings critique of the Senate draft. Cite them as interested parties. Their own
     proposal is not budget-neutral either, so the premium's cost cannot be a disqualifier for
     mine and a detail for theirs — the same standard applies to their $2B.

     UNVERIFIED: the "process measures and lump-sum payments" characterisation is white-paper
     reading, same caveat as the rest of the funding work. -->

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

- [ ] 
- [ ] 

## 7. AI Boundaries

<!-- Per artifact, per AGENTS.md. Which parts are human-first, which are AI-first-verified, which
     are off limits. The brief was human-first. The paper's prose should be too. Say where AI may
     help — structural review, source checking, figure construction — and where it may not. -->

| Artifact | Draft order |
|---|---|
| `analysis/research-paper.pdf` | |
| `drafts/YYYY-MM-DD-draft.md` | |
| figures | |

---

_Skeleton drafted with Claude (2026-09-19). My policy decision — §5 in full, §1's question, and
§3's first paragraph — was written by me and transcribed by Claude (2026-09-20) with the prose
unchanged. Claude's own words, to be rewritten or cut before this is final: §1's scope paragraph,
§3's second and third paragraphs, §4's row 2, and every bracketed open item. §§2, 6, 7 remain
mine to write. See [prompt-log.md](../../prompt-log.md)._

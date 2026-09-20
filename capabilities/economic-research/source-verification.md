# Source Verification — Research Brief

Every factual claim in [`docs/briefs/research-brief.md`](../../docs/briefs/research-brief.md), checked
against the source it cites. The 2026-09-17 kickoff session recorded that the numbers Claude proposed
came from the model's memory and still had to be checked; this is that check.

Verified 2026-09-19. Three sources returned HTTP 403 to automated retrieval (ASHP, Axios, Endpoints
News), so claims resting on them are marked **Needs my eyes** and have to be confirmed from a browser
against the primary document before anything enters the paper.

## Confirmed

| Claim in the brief | What the source says | Source |
|---|---|---|
| Injectable shortages run "nearly three times as long" as oral | Injectable median 4.60 years, oral median 1.59 years — a ratio of 2.89 | ASPE |
| An oral shortage "clears in under two years" | Oral median 1.59 years | ASPE |
| Figure: 4.6 / 4.0 / 2.3 / 2.2 / 1.6 | Injectable 4.60, essential medicines 4.0, non-essential 2.3, topical 2.21, oral 1.59 | ASPE |
| "40% of generic drug markets have only a single manufacturer" | "forty percent of generic drug markets have a single manufacturer supplying the market" | ASPE |
| Intas supplied "more than half the U.S. cisplatin and carboplatin" | "more than half of the U.S. supply of generic cisplatin and carboplatin" | KFF |
| Virginia clinic dosing, 60% then 80% | 60% of optimal dose the week of May 16, raised to 80% after a shipment the following week | KFF |
| "cut average generic prices by more than half between 2016 and 2022" | "The average net price of generic drugs fell by more than half between 2016 and 2022" | KFF |
| "loses money on roughly half its products, up from about a third" | Previously "lose[d] money on about a third of the drugs it produced, but now it's more like half" | KFF |
| Akorn, Teva, and Lannett exited or restructured | Akorn closed all U.S. sites after bankruptcy; Teva pivoted toward brand-name and high-value generics; Lannett filed Chapter 11 | KFF |
| Hamilton Project: $2B, low-interest, partly forgivable | "$2 billion in targeted low-interest loans," "partly forgivable if a company achieves agreed-on milestones" | Hamilton Project |
| Pay-for-performance for buffer inventory and reliable vendors | Rewards hospitals for "building a buffer inventory and selecting vendors that are less likely to experience production disruptions," administered by CMS | Hamilton Project |
| Federal stockpile of drugs with no substitute | HHS "targeted buffer inventory at the national level," first-in-first-out, targeting drugs with "no substitutes" | Hamilton Project |
| 323 active shortages | 323 in Q1 2024, past the previous record of 320 in 2014 | AHA (secondary) |

## Needs fixing

**The 10-15% annual price decline is time-bounded.** The brief presents it as an ongoing rate:
competition "has driven generic prices down an estimated 10-15% a year." Brookings gives that as the
rate "from 2017 to 2018," moderating to "-5% to -10% by 2021." A 2024 analysis it cites found
deflation for generic oral solids as high as 25%. The rate is not one number and has not held steady.
This is the load-bearing figure in the third pillar of the economics section, so it should carry its
own date range.

**The GPO reverse-auction mechanism is not in the cited source.** The brief attributes the reverse
auction and Maximum Allowable Cost structure to Brookings. That piece describes MAC lists — "a fixed
upper limit ... for what the payer or pharmacy benefit manager will pay for a given generic drug,
regardless of which manufacturer is chosen" — but does not discuss GPO reverse auctions at all. Either
find a source that documents the reverse auction, or narrow the claim to MAC lists, which is sourced.

**"Intas voluntarily shut the plant down" does not match the reporting.** What is documented is an FDA
import alert in November 2022 that stalled imports from the facility. The inspection itself ran
November 22 to December 2, 2022 and produced an 11-observation Form 483. A voluntary shutdown and a
forced import alert are different events with different implications, and the brief's argument is
stronger with the second. **Needs my eyes** — confirm the sequence against the FDA warning letter.

**"Nearly two decades" understates the record.** ASHP has tracked shortages since 2001, so 323 is the
highest in 23 years of tracking, not "nearly two decades." **Needs my eyes** on two further claims I
could not verify at all: that the count was "almost double the 2016-2017 level," and that it "had
already run above 300 for eighteen straight months." Both require ASHP's quarterly series.

## Worth adding

**The acid.** FDA investigators found Intas employees destroying original records and raw data not only
by shredding and tearing but by pouring acid on them. FDA described a "cascade of failure." This is a
sharper fact than the shredded documents alone. The brief's "hundreds of trash bags" count does not
appear in the reporting I could reach and should be confirmed against the Form 483 itself.

**The Senate proposal's third requirement.** The brief names two conditions, three-year contracts and
meaningful purchase volumes. The source names a third: providers must "maintain contingency agreements
with alternate manufacturers." The add-on payments also go to "hospitals and physicians," not hospitals
alone. On funding, the source describes eliminating Medicaid inflation rebates and removing rebate caps
in the 340B program, which is not the same as the brief's "loosening Medicaid inflation-rebate caps."

## Sources reached

- ASPE, *Analysis of Drug Shortages, 2018-2023* — https://www.ncbi.nlm.nih.gov/books/NBK611681/
- KFF Health News — https://kffhealthnews.org/health-industry/drugmakers-are-abandoning-cheap-generics-and-now-us-cancer-patients-cant-get-meds/
- Rebitzer & Rebitzer, Brookings — https://www.brookings.edu/articles/when-cheap-becomes-fragile-how-the-race-to-the-bottom-in-generics-undermines-manufacturing-quality-and-what-to-do-about-it/
- Wosińska & Frank, The Hamilton Project — https://www.hamiltonproject.org/publication/policy-proposal/federal-policies-to-address-persistent-generic-drug-shortages/

## Sources still to open myself

- ASHP 2024 Drug Shortages Survey — https://www.ashp.org/-/media/assets/drug-shortages/docs/2024/2024-Drug-Shortages-Survey.pdf
- FDA warning letter, Intas Pharmaceuticals, 2023-07-28 — https://www.fda.gov/inspections-compliance-enforcement-and-criminal-investigations/warning-letters/intas-pharmaceuticals-limited-652067-07282023
- FDA compliance record, Intas — https://www.fda.gov/media/164602/download
- Axios, 2024-04-11 — https://www.axios.com/2024/04/11/drug-shortage-record-high
- Endpoints News — https://endpoints.news/fda-inspection-at-india-pharma-at-center-of-the-cisplatin-shortage-cites-multiple-quality-issues/

---

_Verification run with Claude (2026-09-19) against the sources the brief cites; findings drafted by
Claude, and the four flagged claims remain mine to resolve before they enter the paper.
See [prompt-log.md](../../prompt-log.md)._

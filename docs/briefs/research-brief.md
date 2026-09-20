# Shortages of Cheap Generic Drugs: Cisplatin, Carboplatin, Amoxicillin, and IV Saline

## Why now

I picked this because I've lived it. On the unit, a drug shortage doesn't show up as a headline — it shows up as a pharmacist calling to say we're down to a two-day supply of carboplatin, or that saline is being rationed to trauma and OR cases only. In April 2024, ASHP reported 323 active drug shortages in the U.S., the highest count in nearly two decades and almost double the 2016–2017 level; the count had already run above 300 for eighteen straight months (ASHP, Axios).

The drug that put a face on this was cisplatin. In November 2022, FDA inspectors at an Intas Pharmaceuticals plant in Ahmedabad, India found what amounted to a cover-up: hundreds of trash bags of shredded quality-control documents, along with cleaning and data-integrity violations. Intas voluntarily shut the plant down. The problem was that this one facility supplied more than half the U.S. cisplatin and carboplatin used in roughly 500,000 cancer cases a year, so the shutdown became a national chemo shortage almost overnight (KFF Health News, Endpoints News). Oncologists rationed: one Virginia clinic dropped carboplatin doses for uterine cancer patients to 60% of the optimal level, later raising it to 80% as shipments trickled back in, and doctors elsewhere prioritized curable patients over late-stage ones when supply ran short (KFF Health News). Amoxicillin and IV saline have had their own versions of this same story — a handful of suppliers, a single bad inspection or a single hurricane, and a shortage that hospitals absorb by rationing rather than by paying more.

## The economics

This is a supply-chain fragility problem, but the fragility is manufactured, not accidental. Three things are stacked on top of each other.

First, market structure. FDA reported in 2020 that 40% of generic drug markets have only a single manufacturer, and sterile injectables — chemo drugs, IV fluids, antibiotics given by infusion — are the worst of the group, because building an FDA-approved sterile-injectable line is a large, slow, fixed-cost investment that doesn't pay off unless volume is high and reliable (ASPE analysis of national shortage data, 2018–2023). There's no spare capacity sitting around, so one plant failing an inspection removes supply the rest of the market can't quickly replace.

Second, demand doesn't respond to price the way a textbook market expects it to. A hospital can't decide to buy less carboplatin because it got more expensive — patients need the dose they need. That price-inelastic demand means the usual market signal (price rises, new suppliers enter) works too slowly, if at all, to prevent a shortage, and by the time it might attract entry, the shortage is often already over.

Third, and this is the part I think explains why suppliers keep leaving: hospitals buy generics through group purchasing organizations that run reverse auctions and pay pharmacies on Maximum Allowable Cost lists, which reward whoever bids lowest regardless of whether that manufacturer has the quality systems or backup capacity to stay reliable. That competition has driven generic prices down an estimated 10–15% a year and cut average generic prices by more than half between 2016 and 2022. The generics industry now loses money on roughly half its products, up from about a third historically, and companies like Akorn, Teva, and Lannett have exited or restructured rather than keep making the cheapest, least profitable injectables (KFF Health News; Brookings, "When cheap becomes fragile"). Nobody in that chain is paying for redundancy, so redundancy doesn't exist — which is exactly why a single failed inspection in Ahmedabad can ration chemotherapy in Virginia.

## Figure: why sterile injectables are the ones that ration

Cisplatin, carboplatin, and IV saline are all sterile injectables — exactly the category that stays in shortage longest, by a wide margin.

| Drug type | Median years in shortage |
| --- | --- |
| Injectable | 4.6 |
| Essential medicines | 4.0 |
| Non-essential medicines | 2.3 |
| Topical | 2.2 |
| Oral | 1.6 |

_Data from the embedded chart in the Word original ("Median years in shortage, by drug type"). To be rebuilt as a labeled figure in `analysis/figures/` for the paper._

Source: U.S. Dept. of Health and Human Services, ASPE, Analysis of Drug Shortages, 2018–2023 (NCBI Bookshelf NBK611681), https://www.ncbi.nlm.nih.gov/books/NBK611681/

A shortage of an oral drug like amoxicillin typically clears in under two years, because a tablet line is relatively cheap to stand up and several manufacturers can usually flex into the gap. An injectable shortage runs nearly three times as long, because the fixed cost and lead time to bring on new sterile capacity is so much higher — which is the manufacturing-side mirror of the pricing problem in the section above.

## The policy fight

The idea that's gotten the most traction is some version of a guaranteed-price contract or reliability premium: pay a manufacturer a bit more, in exchange for a multi-year commitment, to keep making a cheap drug reliably rather than exiting the market. The clearest version on the table is a Senate Finance Committee proposal for Medicare add-on payments to hospitals that sign at least three-year contracts, with meaningful purchase volumes, with manufacturers that demonstrate quality and supply reliability (Brookings). A parallel academic proposal from the Hamilton Project would pair $2 billion in low-interest, partly forgivable loans for facility upgrades with a pay-for-performance program that rewards hospitals for holding buffer inventory and choosing reliable vendors, plus a federal stockpile of drugs that have no substitute (Hamilton Project).

The objection is straightforward: this raises costs, and it raises them in a way that locks in whichever manufacturers already hold the contracts. If Medicare or a hospital system is paying a premium for "reliability," someone has to prove that premium is actually buying more capacity and not just protecting an incumbent's margin — and the same GPOs and pharmacy benefit structures that produced the race to the bottom are the ones that would administer the new, higher price. The Senate proposal partly funds itself by loosening Medicaid inflation-rebate caps, which critics say could quietly raise costs elsewhere in the system even as it stabilizes shortage-prone generics (Brookings). My own read, watching this from the hospital side, is that the objection is right about the mechanism and wrong about the conclusion: paying nothing for reliability is also a price, it's just paid later, in rationed chemo doses instead of a line item.

## Why this topic

Of the supply-chain fragility examples in this course, this is the one I don't need a case study to picture — I've stood in the room when a pharmacist says a drug is short, and watched a treatment plan get rewritten around what's actually in the Pyxis rather than what the patient needs. It's also the most quantifiable option on the list: there's a clean number of shortages, a clean price series, a clean manufacturer count, and a specific policy fight with a bill number attached to it, which makes it a good vehicle for applying the actual economics rather than just describing the problem.

## References
- American Society of Health-System Pharmacists. (2024, April). ASHP calls for policy solutions as drug shortages reach all-time high. https://www.ashp.org/about-ashp/ceo-blogs/recent-blogs/ashp-calls-for-policy-solutions-as-drug-shortages-reach-all-time-high
- Axios. (2024, April 11). Drug shortages reach record high. https://www.axios.com/2024/04/11/drug-shortage-record-high
- Endpoints News. (2023). FDA inspection at India pharma at center of the cisplatin shortage cites multiple quality issues. https://endpoints.news/fda-inspection-at-india-pharma-at-center-of-the-cisplatin-shortage-cites-multiple-quality-issues/
- KFF Health News. (2023). Drugmakers are abandoning cheap generics, and now US cancer patients can't get meds. https://kffhealthnews.org/health-industry/drugmakers-are-abandoning-cheap-generics-and-now-us-cancer-patients-cant-get-meds/
- Rebitzer, J. B., & Rebitzer, R. S. (2024). When cheap becomes fragile: How the race to the bottom in generics undermines manufacturing quality and what to do about it. Brookings Institution. https://www.brookings.edu/articles/when-cheap-becomes-fragile-how-the-race-to-the-bottom-in-generics-undermines-manufacturing-quality-and-what-to-do-about-it/
- U.S. Department of Health and Human Services, Office of the Assistant Secretary for Planning and Evaluation. (2025, January 10). Analysis of drug shortages, 2018–2023 [Data brief]. National Center for Biotechnology Information Bookshelf. https://www.ncbi.nlm.nih.gov/books/NBK611681/
- Wosińska, M., & Frank, R. G. Federal policies to address persistent generic drug shortages. The Hamilton Project, Brookings Institution. https://www.hamiltonproject.org/publication/policy-proposal/federal-policies-to-address-persistent-generic-drug-shortages/

---

_Brief written by Allen Mehr. Converted from [originals/research-brief.docx](originals/research-brief.docx) with Claude (2026-09-19); prose unchanged, the Word chart transcribed as a table. See [prompt-log.md](../../prompt-log.md)._

# Source Sheet — Research Paper

Every number the paper can use, where it comes from, and whether it is cleared to go in. Status comes
from [`source-verification.md`](./source-verification.md). **Cleared** = verified. **Check** = needs my
eyes on the primary source first. **Don't use** = contradicted, use the replacement.

## Numbers

| Claim | Number | Source (page) | Status |
|---|---|---|---|
| Entry cost E(CC), generic injectables | $5,921,504 / $9,164,082 / $12,218,777 (low / medium / high) | ASPE ROI, p. 2 | Cleared |
| COGS share of revenue | Injectables 42%, orals 36% (so contribution margin 58%) | ASPE ROI, p. 2 | Cleared |
| Discount rate; dollars | 8.82%; January 2024 dollars | ASPE ROI, p. 3 | Cleared |
| Cohort | Launched July 2018 – July 2021; sales through June 2024 | ASPE ROI, pp. 2–3 | Cleared |
| Months to break-even | 15 / 25 / 36; orals 13 | ASPE ROI, p. 4 (Fig. 1 note) | Cleared |
| ROI at 36 months | 42% / 17% / 0%; orals 55%. Main body only, not the appendix | ASPE ROI, p. 6 | Cleared |
| Share net profitable at 36 months | 40% / 30% / 24%; orals 41% | ASPE ROI, p. 6 (Fig. 3) | Cleared |
| Share underwater at 36 months | 70% (medium). Range 60–76% across scenarios. Say *injectables*, not generics | ASPE ROI, pp. 1, 7 | Cleared |
| Skewed profits | 6 of 447 injectables over $100M net profit; orals 25 of 1,243 | ASPE ROI, pp. 7–8 | Cleared |
| Zero-uplift revenue (my breakeven) | $10.2M / $15.8M / $21.1M | `analysis/required-uplift-u.xlsx` | Cleared |
| Median years in shortage | Injectable 4.60, oral 1.59 (ratio 2.89); essential 4.0, non-essential 2.3, topical 2.21 | ASPE Shortages 2018–2023 | Cleared |
| Single-manufacturer markets | 40% of generic markets. Cite ASPE, not "FDA 2020" as the brief does | ASPE Shortages 2018–2023 | Cleared |
| Intas share of supply | More than half of U.S. cisplatin and carboplatin | KFF Health News | Cleared |
| Virginia clinic rationing | Carboplatin at 60% of optimal dose, then 80% | KFF Health News | Cleared |
| Generic price fall | Average net price fell by more than half, 2016–2022 | KFF Health News | Cleared |
| Annual price decline | 10–15% was 2017–18 only, easing to 5–10% by 2021. Never state it as an ongoing rate | Brookings (Rebitzer) | Cleared, with dates |
| Industry exits | Akorn closed, Teva pivoted, Lannett Chapter 11 | KFF Health News | Cleared |
| Hamilton package | $2B low-interest, partly forgivable loans; buffer-inventory pay-for-performance; federal stockpile | Hamilton Project | Cleared |
| Record shortages | 323 in Q1 2024, past 320 in 2014; highest in 23 years of tracking | AHA (secondary); ASHP | Check |
| Intas events | FDA inspection Nov 22 – Dec 2, 2022, 11-observation Form 483, import alert. Records destroyed, including with acid | FDA warning letter, 2023-07-28 | Check |
| Senate draft funding | Secretary may reduce or waive Medicaid inflation rebates; hospitals certify no 340B discounts; no offset named | Senate Finance May 2024 discussion draft | Check |
| **Dollar cost of shortages** | **None yet. My failure condition needs it** | — | **Missing** |

**Don't use:** "loses money on roughly half its products" (use ASPE's 70% for injectables); "Intas
voluntarily shut the plant down" (it was an import alert); GPO reverse auctions (not in the cited
source, so narrow the claim to MAC lists); "nearly two decades"; any bill number (there is only a
discussion draft); "loosening Medicaid inflation-rebate caps".

**ASPE's own limits, in its words:** it studies *newer* generics, and "older generics are frequently
highlighted as being especially prone to shortage risk" (p. 9). It offers only "suggestive evidence
linking profitability to shortage risk" (p. 3).

## Bibliography (APA 7)

- Holtkamp, N., & Murphy, S. (2024, December). *An examination of the return on investment of generic injectable prescription drugs* [Issue brief]. Office of the Assistant Secretary for Planning and Evaluation, U.S. Department of Health and Human Services. https://www.ncbi.nlm.nih.gov/books/NBK611650/
- KFF Health News. (2023). *Drugmakers are abandoning cheap generics, and now US cancer patients can't get meds*. https://kffhealthnews.org/health-industry/drugmakers-are-abandoning-cheap-generics-and-now-us-cancer-patients-cant-get-meds/
- Rebitzer, J. B., & Rebitzer, R. S. (2024). *When cheap becomes fragile: How the race to the bottom in generics undermines manufacturing quality and what to do about it*. Brookings Institution. https://www.brookings.edu/articles/when-cheap-becomes-fragile-how-the-race-to-the-bottom-in-generics-undermines-manufacturing-quality-and-what-to-do-about-it/
- U.S. Department of Health and Human Services, Office of the Assistant Secretary for Planning and Evaluation. (2025, January 10). *Analysis of drug shortages, 2018–2023* [Data brief]. https://www.ncbi.nlm.nih.gov/books/NBK611681/
- Wosińska, M., & Frank, R. G. (n.d.). *Federal policies to address persistent generic drug shortages*. The Hamilton Project, Brookings Institution. https://www.hamiltonproject.org/publication/policy-proposal/federal-policies-to-address-persistent-generic-drug-shortages/

**Still to complete before the paper goes in:**
- the year for Wosińska & Frank;
- a full reference for the Senate Finance May 2024 discussion draft;
- the Wosińska & Frank Brookings critique of that draft (no URL recorded yet);
- the FDA Intas warning letter (2023-07-28);
- ASHP or AHA for the 323 count;
- a shortage-cost source.

I removed Axios and Endpoints from the brief's reference list. No cleared claim rests on them alone.

---

_Compiled by Claude Code on 2026-09-24 from `source-verification.md`, spec §§2–4, the brief's
references and my copy of the ASPE ROI PDF. Page numbers are from that PDF. See
[prompt-log.md](../../prompt-log.md)._

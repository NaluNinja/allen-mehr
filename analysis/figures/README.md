Charts referenced by the findings in `analysis/`.

- `shortage-duration-by-drug-type.svg` — Figure 1 of the research paper, median years in shortage by drug type, from ASPE 2018–2023 data.

  _Figure 1 was built by Claude Code from ASPE's published values on 2026-09-20. I checked every value against the source and kept each at the precision ASPE published. See [prompt-log.md](../../prompt-log.md), 2026-09-20._

- `required-uplift-u.png` — Figure 2 of the research paper, required price uplift by product revenue under ASPE's low, medium and high entry-cost scenarios. Exported from the chart in [`../required-uplift-u.xlsx`](../required-uplift-u.xlsx).

  _I built the spreadsheet and chart. On 2026-09-24 Claude Code renamed the legend entries to name the entry-cost scenarios and added the dashed medium break-even marker at $15.8M, which reads from the medium zero-uplift revenue cell. See [prompt-log.md](../../prompt-log.md), 2026-09-24._

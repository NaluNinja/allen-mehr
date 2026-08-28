# Prompt Log

A running record of AI sessions that mattered — not every prompt, but the ones that shaped a decision, a draft, or a model.

| Date | Tool | What it was for | Outcome |
|------|------|------------------|---------|
| 2026-08-16 | Claude | Scaffolded portfolio repository structure (README, RESUME, AGENTS, CLAUDE, .gitignore, folder placeholders) per course setup guide | Files drafted for review before committing |
| 2026-08-19 | Claude | Drafted BIO.md (150–200 word bio) per onboarding checklist, using RESUME.md as source material | Draft written for review before committing |
| 2026-08-22 | Claude | Attacked my Stage 1 hypothesis for the perfect-competition case (docs/briefs/perfect-competition-brief.md) — I drafted the problem statement and hypothesis myself; asked the model to name unsupported claims, contradictions, and check labor-hour feasibility against the case's own formula, without rewriting my text | Went through three hypothesis drafts. Caught: (1) reasoning that contradicted my own bed-count numbers, (2) a mix that exceeded the total labor-hour budget by ~1,250 hours, (3) a claim that "not enough worker hours" caused unplanted beds when my own numbers showed labor slack. Final version attributes the tomato stop to marginal cost crossing price, not a labor shortage. |
| 2026-08-26 | Claude | Acted on instructor feedback: add one-line README files for `analysis/`, `docs/`, and a new `capabilities/marginal-analysis/` so each folder explains what it holds instead of showing a bare path on GitHub | Three READMEs drafted, reviewed, and committed (a647710); Stage 1 brief deliberately left untouched, since Stage 3 compares it against the Stage 2 model |

| 2026-08-26 | Claude | Stage 1 brief revision per instructor feedback: add a "How I would know I was wrong" section and name which constraint I expect to bind. I gave my own reasoning on what stops the farm; asked the model to check it and structure it, not to supply the economics | Added both sections. Working through it surfaced that the feedback's summary ("land does not bind, labor does not bind, economics stops you") is right about the idle beds but leaves the crop caps unresolved — carrots and mesclun are stopped by their caps, tomatoes by marginal cost crossing price. Brief now says both. Also learned slack/binding/shadow price, which gives Stage 2 a mechanical check: Solver should report $0 on beds, labor, and the tomato cap, positive on the carrot and mesclun caps. |

## Reflection

<!-- 300 words or fewer. How did you verify what the model told you? What did you check yourself
     rather than take on faith — e.g., did you redo the labor-hour arithmetic by hand, re-check the
     bed-cap numbers against the scenario table, confirm the contradiction was real before revising?
     Write this yourself — do not have AI draft it. -->

## Reflection on verification

I used AI to challenge my first hypothesis rather than to write the final answer for me. I checked the crop limits, total bed limit, labor hours available, selling prices, and diminishing-returns rates against the case materials.

One important part of this process was finding the labor formula in the case instructions. I initially focused mostly on revenue per bed and did not fully understand how quickly labor needs increase as more beds of the same crop are planted. After locating the formula, I reviewed how it uses the number of beds, weekly labor per bed, the 36-week season, and the diminishing-returns rate. This helped me understand why tomatoes may become much more expensive in labor as more tomato beds are added.

My first idea had problems. The numbers did not match my explanation of which crop would receive the most space, and one proposed mix required more labor hours than the farm could provide. I revised the prediction to 10 tomato beds, 20 carrot beds, and 30 mesclun beds. I then checked that these total 60 beds, which is below the 64-bed limit, and reviewed the estimated labor requirement of about 5,277 hours against the 6,480 hours available from the farmer and up to four temporary workers.

I also corrected my explanation of mesclun. Carrots have the lower starting labor requirement, but mesclun’s labor needs increase more slowly as more beds are added. I understand that this is still only a hypothesis, and the spreadsheet model will test whether these predicted bed counts are actually the best choice.

## Reflection 1.2
I came into this project with very little background in accounting, economics, or Excel Solver. I used the professor’s GitHub resources, the Perfect Competition Model website, and AI to help me understand the concepts, work through my hypothesis, and build the model.

There were three build attempts. The first stopped before any cells were written because it found an ambiguity in my own specification. Section 4.4 did not clearly identify the relevant actor. It would have been easy to answer the question in chat and move forward, but then the model would have been based on an assumption not written in my specification. Instead, I updated the specification before proceeding.

The second attempt ran to completion and initially looked successful. However, when I reviewed it, I found that the summary did not accurately report its own data. It reported marginal-cost dips at beds 6, 17, and 14. The flag column showed dips at bed 6, beds 17 and 18, and beds 14 and 15. The summary missed the second dip for both carrot and mesclun.

I could have typed the missing bed numbers into the summary cell, but then the displayed result would not have come from the model itself. I found other issues in that version as well, so I discarded the completed workbook rather than patching it. The third attempt was rebuilt from scratch and became the submitted version.

The final model matched check figures already included in the specification. That was reassuring, but it was not independent validation because the builder knew the target values before creating the workbook. I would still want to compare the results with Farm Profit Lab or another method.

The main lesson was that AI helped me build much more than I could have alone, but I still had to verify that the output actually matched the model.
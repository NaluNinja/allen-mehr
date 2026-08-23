# Prompt Log

A running record of AI sessions that mattered — not every prompt, but the ones that shaped a decision, a draft, or a model.

| Date | Tool | What it was for | Outcome |
|------|------|------------------|---------|
| 2026-08-16 | Claude | Scaffolded portfolio repository structure (README, RESUME, AGENTS, CLAUDE, .gitignore, folder placeholders) per course setup guide | Files drafted for review before committing |
| 2026-08-19 | Claude | Drafted BIO.md (150–200 word bio) per onboarding checklist, using RESUME.md as source material | Draft written for review before committing |
| 2026-08-22 | Claude | Attacked my Stage 1 hypothesis for the perfect-competition case (docs/briefs/perfect-competition-brief.md) — I drafted the problem statement and hypothesis myself; asked the model to name unsupported claims, contradictions, and check labor-hour feasibility against the case's own formula, without rewriting my text | Went through three hypothesis drafts. Caught: (1) reasoning that contradicted my own bed-count numbers, (2) a mix that exceeded the total labor-hour budget by ~1,250 hours, (3) a claim that "not enough worker hours" caused unplanted beds when my own numbers showed labor slack. Final version attributes the tomato stop to marginal cost crossing price, not a labor shortage. |

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

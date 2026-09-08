<!-- PR TARGET: https://github.com/NaluNinja/allen-mehr | Stage 1.3 -->
# Stage 1.3 review — analysis, memo, prompt log

> **Hurricane Lowell comes first.** If you are preparing, sheltering, travelling, or helping somebody else do one of those, put this review down — it will keep, and nothing in it needs your attention while that does. Look after your people first; we will sort the coursework out afterwards.

**Analysis:** [`analysis/perfect-competition-analysis.md`](https://github.com/NaluNinja/allen-mehr/blob/main/analysis/perfect-competition-analysis.md)

> Graded 2026-09-08 against the analysis, memo, figures and prompt log you committed. I recomputed your carrot and mesclun schedules independently, bed by bed, because several of your claims go past what the assignment says — and every one of them is right, including the two that contradict the brief.

| Criterion | Where it stands |
|---|---|
| P = MC evidence and binding constraints | Full marks. Crossings and shadow prices from your own schedules, all three slack constraints named with numbers, and you are the only person in the cohort who keeps the gap at the cap and the value of the next bed as two separate quantities instead of conflating them. |
| MC dip and the at-a-loss resolution | Full marks, and past them. You show the dip is not a tomato peculiarity but a general consequence of crossing the farmer's hours, then explain why it lands on one bed for tomatoes and two for the others. The at-a-loss section corrects the assignment's own claim. |
| Figures and the hypothesis revisit | Full marks. Three figures, each referenced where it earns its place. The hypothesis revisit separates predictions that were genuinely independent from ones that merely matched a check figure I had already published, which almost nobody thinks to do. |
| Prompt log and reflection | Curated, dated, and honest about a conclusion you later reversed. The reflection traces a one-cent discrepancy back to the workbook to work out which of the two numbers was wrong. What is still open below. |

### You found two errors in the assignment

Your analysis says the workbook does not support the assignment's statement that every crop loses money alone or that price exceeds average variable cost at every quantity. Both halves of that are correct, and I have checked both in exact arithmetic.

Tomatoes are profitable standalone from 7 through 13 beds, peaking at $6,172.77 at 10 beds. The brief says every crop loses money at every quantity. It is wrong.

Mesclun average variable cost exceeds its $2,700 price at bed 13 and at bed 14 — $2,716.35 and $2,702.51 — and nowhere else in a thirty-bed schedule. The brief says price exceeds average variable cost everywhere. It is wrong, and the exception is two quantities wide out of thirty.

Finding the first one takes attention. Finding the second one takes running the schedule yourself and reading every row, because there is no reason to suspect it is there. I am correcting the brief for both.

### The dip generalises, and you proved it

The assignment presents the marginal-cost dip as a tomato result and calls it the most interesting thing in the model. You showed it is not a tomato result at all — carrots dip at beds 17 and 18, mesclun at beds 14 and 15, and all three dips are the same event, the standalone schedule crossing the farmer's 720 hours.

Then you answered the question that makes it a finding rather than an observation: why one bed for tomatoes and two for the others. Because the threshold lands in a different place inside the crossing bed. Tomato bed 5 is 97.6 per cent farmer-priced, so marginal cost still rises through it and the fall shows up whole on bed 6. Carrot bed 17 is 88.3 per cent temporary-priced, so the fall starts inside the crossing bed and continues into the next.

I checked all of it: 712.563 and 776.025 hours for carrots at beds 16 and 17, 687.529 and 749.671 for mesclun at 13 and 14, marginal costs of $1,670.90, $1,589.14, $2,522.58 and $1,983.96. Exact.

Your log is honest about the route: on 30 August you recorded that the mechanism did not generalise, and on 3 September you recomputed and reversed yourself. Writing down that you were wrong, in the same document, is worth more than having been right first time.

### The distinction nobody else made

You report carrot marginal cost at bed 20 as $1,688.95, which leaves $405.05 under the $2,094 price — and separately report the shadow price of the cap as $352.49. Both numbers are in your analysis and they are not the same number, because they answer different questions.

$405.05 is how far under price the last bed you were allowed to plant came in. $352.49 is what the next bed would be worth if the cap moved. The first is about the bed you have; the second is what you would pay for one more.

That distinction is the single most common place this case goes wrong, and you are the only person who kept both quantities and labelled them. It is also why your memo can say what the farmer should pay per bed of added capacity without ambiguity.

### Where the point went

Nothing substantive. Your prompt log still carries the template's instruction comment — the block beginning "300 words or fewer" — and three reflections stacked one after another, from Stage 1.1, Stage 1.2 and this stage, under headings that do not quite agree with each other.

The graded reflection is the Stage 3 one and it is 286 words, comfortably inside the limit. But a reader arriving cold has to work out which of the three is current, and the leftover instruction comment is the sort of thing that gets read as carelessness by somebody who does not know how good the rest of the document is.

Delete the comment block, and give each reflection a heading that names its stage. Two minutes.

### One honest thing i want to acknowledge

You recorded that the memo was reviewed while you were drafting it rather than after a control commit, so there is no uncommitted control version — and you put that in the commit message rather than letting the cleaner story stand.

The rule for this stage is human-first, and reviewing while drafting sits closer to the line than reviewing after. You knew that, said so, and named the clean pattern for next time. I am not taking anything for it, because a documented deviation that a reader can evaluate is not the problem the rule exists to prevent. An undocumented one is.

---

### How to work this review

Treat this PR the way an analyst treats feedback from a senior reviewer — a review is a proposal to engage with, not a checklist to rubber-stamp.

1. **Read it yourself first.** Form your own view before you change anything. Disagreeing *with a documented reason* is a legitimate, senior response.
2. **Stress-test it with an LLM.** Paste this review and your analysis into your assistant and ask it to (a) explain anything you are unsure of, and (b) argue the *other side* — where might the reviewer be wrong, and what would you give up by making each change.
3. **Then write the changes yourself.** The analysis, the memo and the reflection are yours to draft. An explanation you did not reason through cannot be defended when somebody asks you a follow-up question about it.
4. **Close the loop.** Reply in this thread with what you changed and what you pushed back on, then commit and push.

*Your score and the per-criterion breakdown are in your Lamaku comment, not here — this repository is public.*

— Adam

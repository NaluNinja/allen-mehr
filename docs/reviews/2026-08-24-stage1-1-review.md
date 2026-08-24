<!-- PR TARGET: https://github.com/NaluNinja/allen-mehr | Stage 1.1 (2.5 pts) -->
# Stage 1.1 review — engagement brief · **92 / 100** (A-) · 2.30 / 2.5 pts

**Brief:** [`docs/briefs/perfect-competition-brief.md`](https://github.com/NaluNinja/allen-mehr/blob/main/docs/briefs/perfect-competition-brief.md)

| Criterion | Earned | Notes |
|---|---|---|
| Problem restated in your own voice | 27 / 30 | Clean and genuinely restated rather than paraphrased. You lead with the price-taking constraint — "It cannot control what customers pay, so its decision is limited to choosing the crop mix" — which is the fact the whole case turns on. The small gap is that you name the resources without saying which one you expect to bind; the constraint that stops you is the interesting part. |
| Hypothesis names a specific mix | 25 / 25 | About 10 tomato / 20 carrot / 30 mesclun. Specific, committed, and you say what happens to the leftover four beds. |
| Economic mechanism | 25 / 25 | This is the best short mechanism in the cohort. You name the driver (labor need rising faster per tomato bed), the test (the next bed costing more than its $8,800 price), and then the sentence that earns the full mark: the four beds go unused "not because the farm runs out of workers, but because the remaining available tomato beds are no longer worth planting." That is exactly the distinction between a binding resource constraint and P = MC, and most of this cohort will not make it until Stage 3. |
| Falsifiability and process | 15 / 20 | The prediction is sharply checkable — 10 beds, four idle, for a stated reason — so it is falsifiable in substance. But the brief has no "how I would know I was wrong" section, and writing it down is what makes the Stage 3 comparison mechanical rather than a matter of memory. Brief committed 2026-08-23 with no modeling work before it. Correct path. |
| **Final** | **92 / 100** | earned on merit |

### What I'd fix first

- Add a short "How I would know I was wrong" section. You are most of the way there already — the material is in your hypothesis. Turn it into named outcomes: tomatoes reaching their 20-bed cap would mean the labor penalty is milder than you think; carrots or mesclun finishing below their caps would mean something other than diminishing returns is binding first. Three bullets, ten minutes, and Stage 3 gets much easier.

- One sentence on which constraint you expect to bind. You have 64 beds, caps of 20/20/30 that sum to 70, and up to 6,480 labor hours. Say which of those you think actually stops the farm. Your own hypothesis implies the answer — you predict four idle beds, so you are saying land does not bind and labor does not bind, and economics stops you instead. Making that explicit is worth doing because it is a strong, checkable claim.

### Looking ahead to Stage 2

Your brief is now frozen. If the model disagrees with it, do not go back and edit this file — the gap between prediction and result is the raw material for Stage 3, and it is worth more than being right.

Stage 2's deliverable is a spec in capabilities/marginal-analysis/ before the workbook exists, plus an audit of what the AI builds from it. The reasoning in this brief is exactly the reasoning that spec needs.

---

### How to work this review

Treat this PR the way an analyst treats feedback from a senior reviewer — a review is a proposal to engage with, not a checklist to rubber-stamp.

1. **Read it yourself first.** Form your own view before you change anything. Disagreeing *with a documented reason* is a legitimate, senior response.
2. **Stress-test it with an LLM.** Paste this review and your brief into your assistant and ask it to (a) explain anything you are unsure of, and (b) argue the *other side* — where might the reviewer be wrong, and what would you give up by making each change.
3. **Then write the changes yourself.** For a brief, this matters more than usual: a hypothesis you did not generate cannot be honestly compared against your model in Stage 3, and that comparison is the entire point of writing the brief first.
4. **Close the loop.** Reply in this thread with what you changed and what you pushed back on, then commit and push.

*One standing rule for this stage: do not revise your hypothesis to match what your model later tells you. If the model contradicts the brief, that is a finding, not an error — Stage 3 asks you to explain the gap, and a brief quietly edited to be right afterwards has nothing left to explain.*

— Adam

<!-- PR TARGET: https://github.com/NaluNinja/allen-mehr | Stage 1.1 (2.5 pts) -->
# Stage 1.1 review — engagement brief · **97 / 100** (A+) · 2.43 / 2.5 pts

**Brief:** [`docs/briefs/perfect-competition-brief.md`](https://github.com/NaluNinja/allen-mehr/blob/main/docs/briefs/perfect-competition-brief.md)

> Re-graded 2026-08-27. Your previous score was 92. The five points were all in one place — no "how I would know I was wrong" section — and you did not just add one, you added the constraint analysis underneath it. This is now the strongest brief in the cohort after Day's.

| Criterion | Earned | Notes |
|---|---|---|
| Problem restated in your own voice | 27 / 30 | Unchanged and still clean. You lead with the price-taking constraint — "It cannot control what customers pay, so its decision is limited to choosing the crop mix" — which is the fact that makes this a perfect-competition case rather than a pricing one. The three points off are the same as before: the statement is efficient to the point of being spare. You name the caps as "a maximum number of beds" without giving the numbers, and the 36-week season and the $20,000 appear as "fixed seasonal costs" rather than as figures. A reader who has not read the case cannot reconstruct the problem from your paragraph. |
| Hypothesis names a specific mix | 25 / 25 | About 10 tomato, 20 carrot, 30 mesclun. Specific, committed, and you say what happens to the leftover four beds rather than letting them go unmentioned. |
| Economic mechanism | 25 / 25 | Still the best short mechanism in the cohort, and the new constraint section deepens it. You name the driver, the test, and then the sentence that earns the full mark: the four idle beds are idle because the eleventh tomato bed costs more than $8,800, not because the farm ran out of land or hours. Distinguishing "stopped by a constraint" from "stopped by economics" is the central distinction in this case and you are the only person who wrote it down before building anything. |
| Falsifiability and process | 20 / 20 | Three named outcomes, each tied to the specific assumption it would break, and one of them is aimed at your own central claim rather than at a detail: "All 64 beds are planted, or the labor hours are used up... then land or labor is what stops the farm after all, and my explanation is wrong." Writing the test that could take down your own thesis is the hard version of this criterion and it is the one that earns full marks. The brief is at the correct path, the revision is dated and attributed in the file itself, the AI session is logged, and the whole thing predates your spec by a day — the order this stage requires. |
| **Final** | **97 / 100** | earned on merit |

### What the new sections added

The "Which Constraint I Expect to Bind" section is the piece of work here, and it is worth saying why rather than just marking it correct.

Most briefs in this cohort predict a mix. Yours predicts a mix and then asks the second question: what is it that stops the farm? You then rule out land (60 of 64 beds planted, so space was still available), rule out labor (hours still left over when planting stops), and conclude that the only thing left is economics. That is an argument by elimination over the three candidate binding constraints, and it is exactly how a decision memo should be structured.

You also split the crops correctly: tomatoes stop on price, carrots and mesclun stop on their caps, and you say what would happen if the caps were raised. That last point is the shadow-price question, and it is a Stage 3 deliverable that you have already framed.

### One thing to be careful about, and it matters for Stage 3

Your brief says you expect "about 5,277 of the 6,480 available hours" to be used. The published check figures are available to everyone and using them is not against the rules, so this costs you nothing here. But a prediction quoted to four significant figures from the answer key is not really a prediction, and Stage 3 is where that becomes a problem: it asks you to compare what you expected against what your model found, and "I expected 5,277 hours and got 5,277 hours" is not a comparison, it is a tautology.

The parts of your brief that are genuinely yours — the elimination argument, the claim that four beds sit idle for economic rather than physical reasons, the three falsification conditions — are not in the check figures and cannot be read off them. Those are what Stage 3 should be built on. When you write that memo, be explicit about which of your predictions were reasoned and which were taken from the published figures. Saying so plainly will be worth more than a memo that blurs the two, and a reviewer will notice the difference whether or not you point it out.

For the record, the mechanism you gave for the tomato stopping point is right, and it is right for reasons the check figures do not supply. That is the part to defend.

### Where this leaves you

Your Stage 1.2 spec is graded separately and it is one of the two strongest in the cohort. The connection between the two documents is the thing to protect: your spec's §5.5 says the constraint-status block "exists because the Stage 1 brief made a specific claim about which constraints bind." That is a spec written to test a hypothesis rather than to produce an answer, and it is the whole architecture of this project working as intended.

One standing rule from here on: do not revise this brief to match what the model tells you. If the model contradicts it, that is a finding. Stage 3 asks you to explain the gap, and a brief quietly edited to be right afterwards has nothing left to explain.

---

### How to work this review

Treat this PR the way an analyst treats feedback from a senior reviewer — a review is a proposal to engage with, not a checklist to rubber-stamp.

1. **Read it yourself first.** Form your own view before you change anything. Disagreeing *with a documented reason* is a legitimate, senior response.
2. **Stress-test it with an LLM.** Paste this review and your brief into your assistant and ask it to (a) explain anything you are unsure of, and (b) argue the *other side* — where might the reviewer be wrong, and what would you give up by making each change.
3. **Then write the changes yourself.** For a brief, this matters more than usual: a hypothesis you did not generate cannot be honestly compared against your model in Stage 3, and that comparison is the entire point of writing the brief first.
4. **Close the loop.** Reply in this thread with what you changed and what you pushed back on, then commit and push.

*One standing rule for this stage: do not revise your hypothesis to match what your model later tells you. If the model contradicts the brief, that is a finding, not an error — Stage 3 asks you to explain the gap, and a brief quietly edited to be right afterwards has nothing left to explain.*

— Adam

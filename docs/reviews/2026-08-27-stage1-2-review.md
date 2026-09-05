<!-- PR TARGET: https://github.com/NaluNinja/allen-mehr | Stage 1.2 -->
# Stage 1.2 review — spec, build, audit

**Spec:** [`capabilities/marginal-analysis/spec.md`](https://github.com/NaluNinja/allen-mehr/blob/main/capabilities/marginal-analysis/spec.md)

> Re-graded 2026-08-31. You have been reviewed on this before.5, held because there was no workbook. There is one now, I opened it and checked it against my own figures rather than against your audit, and it reconciles to the cent. This is the first complete Stage 1.2 in the cohort with an audit trail behind it, and the audit is the reason for the score.

| Criterion | Where it stands |
|---|---|
| Spec completeness — inputs, structure, calculation flow | Buildable from this file alone and now considerably more so than a week ago. Every convention that could have been invented by a builder is written down instead: the derived-input rule, the wage denominator, the temp-hours contract, the permanent-then-temporary costing order, the discrete marginal-cost definition, the crossing rule, and the tolerances. The section that earns the last half point is the one requiring the MC Schedules sheet to be independent of the mix — a rule that is invisible until it is violated, at which point every standalone schedule in the workbook is quietly wrong. |
| Spec validation rules | Still the best validation section in the cohort and still for the same reason: two labor anchors rather than one. A defective builder that drops the exponent and writes a flat (1 + dim) reproduces q = 1 exactly and fails only at q = 10, and you wrote that reason into the spec rather than just the number. Two students have now adopted that second anchor after seeing it, and one completed workbook in this cohort has exactly the defect it was designed to catch. |
| Workbook satisfies the contract | I checked this myself against my own figures, not against your audit. Optimal mix 10 / 20 / 30 at 60 beds. Season profit $42,761.664682745. Total labor hours 5,277.216114273888, split 720 permanent and 4,557.216114273888 temporary. Temporary workers 3.1647334126902. Blended rate $19.729784239010844. Per-crop labor hours 2,334.368214090002, 983.1698641742373, and 1,959.6780360096488. Every one of those matches to the last digit I hold. |
| Audit note | Five checks, each naming what it would have caught, and one of them is a different order of thoroughness from anything else submitted — see below. |

### On the workbook itself

Beyond the numbers: 103 defined names, all lowercase and consistent; 1,039 formulas with zero direct cell-address references; zero uses of ROUND, TRUNC, or INT anywhere, which is why the figures carry to twelve decimal places instead of quietly settling on a rounded value that propagates; zero error cells; and the per-crop labor allocation summing to labor_cost_total exactly, with that reconciliation built into the sheet as a control rather than checked once by hand.

The internal check at Mix — "farmer_hrs_field x farmer_wage = 25,000, PASS" — is the one I want to point at. It is not a check that the case asked for. It is a check that the farmer's field labor comes to exactly half her salary, which is the arithmetic identity that makes the whole permanent-then-temporary convention coherent. Building a control for an identity you derived yourself is what separates a workbook that produces an answer from one that defends it.

### The cross-check

You compared 712 workbook values against the Farm Profit Lab — 12 at the optimum and 700 across every row and column of all three marginal-cost schedules — and reported zero disagreements with a maximum absolute difference of 5.8e-11. The stage asks for at least one intermediate value. You did seven hundred and twelve.

What makes it a real check rather than a large one is that the Lab is a separate implementation in a different language that enumerates all 13,671 feasible combinations rather than optimizing, and you did not consult it while building. Two independent implementations agreeing to eleven decimal places is evidence of a kind that no amount of re-reading your own formulas can produce.

The shadow-price finding is the best paragraph in the document. You noticed that raising all three caps together produced $598.968554 while the three separate effects summed to $598.968553, one ten-thousandth of a cent apart, and rather than shrugging at it you traced it: the recorded $352.50 and $246.48 were Solver's two-decimal display values, and the exact figures are $352.494754 and $246.473799. So the apparent non-separability was a display artifact, not a property of the model.

That distinction — is this a real interaction between the constraints, or is it rounding — is exactly the question a reviewer would ask, and you had already answered it in writing. You also recorded the one thing the cross-check does not cover, the per-crop allocation block, and named the control that does cover it. Stating the boundary of your own evidence is rarer than producing the evidence.

### What you did not do, and should not have

You recorded that tomato marginal cost falls at bed 6, carrot at beds 17 and 18, and mesclun at beds 14 and 15 — and then wrote that explanation is reserved for Stage 3.

That is the correct call and I want it on the record that it was deliberate. Stage 2 establishes what the model says; Stage 3 explains why. A model whose author has already decided what the anomalies mean tends to produce evidence for that meaning.

You also correctly treated the published check figures as confirmation rather than validation, and said so: a workbook built while knowing the target can match the target for the wrong reasons, and only the independent implementation rules that out. That sentence is the most sophisticated thing anyone has written about their own evidence in this course.

### One caution for Stage 3

Your workbook is finished and your analysis and memo are already committed, which puts you well ahead. The risk that comes with being ahead on this particular case is specific: your Stage 1.1 brief predicted a mix, the model returned one, and Stage 3 grades the honesty of the comparison between them rather than the accuracy of the prediction.

Do not smooth that comparison. If your brief and your model disagree anywhere — the mix, the binding constraint, where the crossing sits — the gap is the finding, and it is worth more than agreement would be. You have the prompt log and the commit history to prove what you believed beforehand, which most of this cohort will not.

### A note on the point value, new as of today

This stage is now worth real marks rather than the 8 in the stage brief, and Stage 1.3 — the analysis, the memo, and the prompt log — is now worth 15 as well. That is because Cases 2 and 3 have been dropped for this cohort, so Case 1 is the case.

What that means in practice: this stage and the next one are together worth 30 of the 35 points on the case. Stage 0 and Stage 1.1 are 2.5 each. The weight has moved onto the build and the analysis, which is where the work actually is.

Nothing about the grading changes — the scoring is unchanged and is converted at the end. The stage brief and the case page still show the old numbers; they have not been updated yet.

---

### How to work this review

Treat this PR the way an analyst treats feedback from a senior reviewer — a review is a proposal to engage with, not a checklist to rubber-stamp.

1. **Read it yourself first.** Form your own view before you change anything. Disagreeing *with a documented reason* is a legitimate, senior response.
2. **Stress-test it with an LLM.** Paste this review and your spec into your assistant and ask it to (a) explain anything you are unsure of, and (b) argue the *other side*.
3. **Then correct the spec, not the workbook.** When a check fails, you fix the specification and regenerate, so the document keeps describing what was actually built.
4. **Close the loop.** Reply in this thread with what you changed and what you pushed back on, then commit and push.

*Your score and the per-criterion breakdown are in your Lamaku comment, not here — this repository is public.*

— Adam

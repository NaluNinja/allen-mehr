# Perfect Competition Analysis

## Optimal planting plan

The optimized planting plan is 10 beds of tomatoes, 20 beds of carrots, and 30 beds of mesclun. I used 60 of the farm’s available 64 beds and produced a season profit of $42,761. I had 4 unused beds, so the physical space is not the constraint that determines the final crop mix. The tomatoes stop because their marginal cost (MC) eventually exceeds the price, while carrots and mesclun stop because their crop-specific caps prevented me from planting any more.

## Why tomatoes stop at 10 beds

Tomatoes had the highest price per bed at $8,800. The high revenue from an additional bed is not just about going for the highest-priced bed; the decision is whether the next bed adds revenue greater than its MC.

The 10th tomato bed remains profitable because its MC is $8,248.59, which is below the $8,800 cut-off. The 11th bed does not meet the test, and its MC is approximately $9,400, or almost $600 above price. The model stops at 10 beds because bed 10 is the last tomato bed where marginal revenue exceeds MC.

Figure 1 shows the tomato MC schedule crossing the price line between beds 10 and 11.

![Figure 1. Tomato marginal cost and price by planted bed.](figures/tomato-mc-price.png)

The four unused beds reflect that additional tomato output is no longer profitable at the margin.

## Binding constraints and expansion value

The carrot and mesclun crop caps are the binding constraints. I planted all 20 permitted carrot beds and all 30 permitted mesclun beds. In contrast, the total-bed limit is slack at 60 of 64 beds, the tomato cap is slack at 10 of 20 beds, and temporary-worker capacity is slack at about 3.16 of the four available workers.

The shadow price of one additional carrot bed, meaning relaxing a binding constraint by one unit while I hold the rest of the model’s assumptions constant, is about $352.49, while the shadow price of one additional mesclun bed is about $246.47. These are local values. If the farm can relax only one production limit, it should seek one additional carrot bed first because that constraint has the larger marginal value. The farm does not need more land to house that capacity because four beds are already unused.

The crop caps stop production before the marginal economics do. At bed 20, carrot MC is $1,688.95, which remains $405.05 below the $2,094 carrot price. At bed 30, mesclun MC is $2,420.10, still $279.90 below the $2,700 mesclun price. Each next unit remains profitable, but the farm is prevented from adding it by the production caps.

Figure 2 shows carrot MC remains below price at the 20-bed cap.

![Figure 2. Carrot marginal cost and price by planted bed.](figures/carrot-mc-price.png)

Figure 3 shows mesclun MC remains below its $2,700 price through the 30-bed cap.

![Figure 3. Mesclun marginal cost and price by planted bed.](figures/mesclun-mc-price.png)

This supports the shadow-price result and distinguishes a binding policy or production cap from an economic stopping point such as the tomato crossing.

## Why tomato MC falls at bed 6

The tomato MC schedule has an unusual decline at bed 6. MC rises from $6,703.12 at bed 4 to $7,660.86 at bed 5, then falls to $4,906.28 at bed 6 before rising again. This is not because tomato production becomes physically less labor-intensive. Total labor requirements continue to rise: 527.076 hours at four beds, 724.730 at five beds, 956.643 at six beds, and 1,227.692 at seven beds.

The explanation is the farm’s two-tier labor system. The farmer can provide only 720 field hours and is paid at an effective field-labor cost of $34.7222 per hour. Temporary labor costs $17.3611 per hour. The 720-hour threshold is crossed during the fifth tomato bed. Bed 5 still uses the remaining farmer hours and only 4.73 temporary hours, so much of its incremental cost is charged at the higher farmer rate.

The sixth bed requires an additional 231.913 labor hours, all of which are supplied by lower-cost temporary workers because the farmer’s field-hour capacity has already been exhausted. That change in the price of the labor input more than offsets the continued increase in required labor hours, causing MC to decline at bed 6. The dip is therefore due to a transition in labor force, not evidence against diminishing returns in the physical production process.

## Standalone losses and shutdown logic

My workbook does not completely support the assignment’s statement that every crop loses money when operated alone or that price exceeds Average Variable Cost (AVC). AVC is the variable cost per bed; if price remains above AVC, production covers its avoidable costs and can still contribute toward fixed costs even when standalone total profit is negative.

That discrepancy matters because the shutdown-rule analysis should follow the modeled results rather than a blanket description of the case.

As an example, carrots lose money ($16,488.92) at 20 beds when treated as a separate business because they do not cover all of the farm’s fixed expenses. However, each carrot bed earns enough to pay for the extra labor, fertilizer, and other costs of growing it. It also leaves some money to help pay farm costs that exist whether carrots are grown or not. Therefore, in the short run, growing carrots is better than stopping production entirely even though carrots alone still show an overall loss.

Mesclun also loses money if treated as a separate business, reaching its least-negative result of $11,922.19 below zero at 30 beds. Its shutdown-rule pattern is qualified, however: mesclun AVC exceeds its $2,700 price at quantities 13 and 14, where AVC is $2,716.35 and $2,702.51. Thus, mesclun is not an example of price exceeding AVC at every quantity, although it remains part of the optimal mixed plan.

Tomatoes should not be included in the “grow at a loss” category. Tomato production is profitable on a standalone basis from 7 through 13 beds and reaches a maximum standalone profit of $6,172.77 at 10 beds. Tomatoes stop at 10 in the mixed solution because their MC crosses price at the next bed, not because they fail the shutdown test.

## Comparison with Stage 1

The Stage 1 expectation that the farm would not exhaust total labor capacity was somewhat correct, but incomplete. The earlier reference to approximately 5,277 labor hours was a published check figure rather than an independently generated prediction, so matching it should not be treated as confirmation of a forecast.

The more useful finding is that aggregate slack hides a binding lower-level allocation. Although the farm does not use all 6,480 available labor hours, it does use all 720 of the farmer’s field hours. Of the 5,277 total hours used in the optimized plan, temporary workers provide the remaining 4,557 hours. This distinction helps explain both the optimal crop mix and the dips in tomato marginal cost. The model therefore supports the broader conclusion that the farm is not constrained by total beds or total labor alone, while correcting the earlier assumption that “labor slack” completely described the relevant operational constraint.

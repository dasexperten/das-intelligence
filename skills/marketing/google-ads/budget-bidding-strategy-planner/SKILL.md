# Budget Bidding Strategy Planner

## Purpose

Choose and adjust Google Ads budgets and bidding strategies based on business goal, measurement quality, conversion volume, value differences, margin, and growth constraints.

## When to Use

Use this skill when selecting between Maximize clicks, Maximize conversions, Target CPA, Maximize conversion value, Target ROAS, or manual controls; reallocating budget; or diagnosing budget-limited campaigns.

## Inputs

Useful inputs: business goal, campaign type, conversion actions, conversion values, recent conversion volume, spend, CPA, ROAS, margin, budget limits, seasonality, and growth target.

## Workflow

1. Confirm the business goal and measurement readiness.
2. Choose value-based bidding when conversion values differ and are reliable.
3. Choose conversion-based bidding when conversions have similar value and CPA is the main control.
4. Use click-focused strategies only when qualified traffic is genuinely the objective or conversion data is not ready.
5. Allocate budget toward campaigns with reliable incremental value, not only the best historical average.
6. Change targets and budgets gradually, document the date, and allow sufficient conversion cycles.

## Output

Always provide recommended bidding strategy, budget allocation, target logic, readiness gaps, learning-period notes, guardrails, and next actions.

## Common Mistakes

- Selecting Target ROAS without reliable conversion values.
- Setting Target CPA or Target ROAS far beyond recent performance.
- Moving budget based only on short-term averages.
- Making frequent target changes before the system can learn.

## Related Skills

- google-ads-performance-director
- google-ads-roas-optimizer
- google-ads-cpa-optimizer
- google-ads-experiment-planner

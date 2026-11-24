# Duka live dashboard

## Status

**Pending Google sign-in and dashboard creation.** No public Looker Studio URL or authentic screenshots are available yet. The static board report is not a substitute for this required interactive report. Do not submit a fabricated link or treat the static chart images as dashboard screenshots.

## Prepared data

Import `outputs/duka_dashboard_data.csv` into Google Sheets, then connect that sheet to Looker Studio. `order_date` must be a Date (exported as YYYY-MM-DD); revenue, quantity and unit_price must be numeric. `order_id` is an identifier used for Count Distinct. Refresh the connected sheet if regenerated data changes.

## Layout and field definitions

| Element | Dimension | Metric / formula |
|---|---|---|
| Revenue scorecard | None | SUM(revenue) |
| Orders scorecard | None | COUNT_DISTINCT(order_id) |
| Average order value scorecard | None | SUM(revenue) / COUNT_DISTINCT(order_id) |
| Monthly trend | order_date with Month granularity | SUM(revenue) |
| Branch sorted bar | branch | SUM(revenue), descending |
| Product sorted bar | product | SUM(revenue), descending |
| Date-range control | order_date | Apply to every scorecard/chart |
| Channel drop-down | channel | Apply to every scorecard/chart |

Use grey for context, PLP redberry #8E0000 for the key highlight and #0BA184 sparingly as accent. Keep units in KES, use a zero baseline on bars, direct labels where readable and a source line: “Duka generator, seed 2026; synthetic orders; 1 January–29 June 2026”. Titles referring to fixed H1 findings should be labelled “H1 reference” or rewritten as filter-aware question titles, so filtering does not make a static insight false.

## Validation targets

- Unfiltered H1: KES 71,792,500 revenue, 1,000 distinct orders, KES 71,792.50 average order value.
- Online filter: KES 22,786,100 revenue, 320 distinct orders, KES 71,206.5625 average order value.
- Confirm that changing channel and date range updates all scorecards and all three charts.
- Confirm date data types, mobile legibility and no duplicated orders.

## Evidence to add after publishing

1. Set viewer access to anyone with the link and verify the report opens as a viewer.
2. Add the actual public report URL here.
3. Save `figures/dashboard_overview.png`, an authentic screenshot showing scorecards, monthly trend, breakdowns and controls.
4. Save `figures/dashboard_filtered.png`, showing the Online-filtered state and its changed metrics.
5. Embed those screenshots here using Markdown image references and record the filter test result.

These are outstanding requirements, not completed actions.

# Validation and Assumptions

## Validation checks and findings

| Check | Treatment / finding |
|---|---|
| Reporting periods | Quantity, INR-value, USD-value, and price series checked for month alignment. Trade-value analysis covers April–July; August volume is used for forecast validation. |
| Categories | Product/category labels checked across the quantity and value inputs before comparison. |
| Units and scale | Volume treated as thousand metric tonnes in source fields; values as ₹ crore and USD million; Indian Basket as USD/barrel. Conversions are applied explicitly when calculating unit costs. |
| Import totals and subtotals | Displayed import product values were reconciled against reported import subtotals/totals where comparable. |
| Source discrepancy | Reported total product export values differed from the sum of displayed product-export rows for April–July 2026. The source total was retained and the difference documented; it was not silently corrected. This is a source-quality observation, not an export analysis. |
| Missing values | August INR and USD import values were unavailable in the validated value workbooks. They remain unavailable; no estimates are introduced. |
| Arithmetic | Ratio calculations, totals, and month-over-month changes are checked for consistent units and nonzero denominators. Derived indicators are not substituted for source measures. |
| Forecast back-test | August actual volume of 21.73 M MT compared with tested approaches. The two-month moving average forecast 23.05 M MT, with 6.07% APE, the lowest among the tested simple methods. |

## Assumptions

1. PPAC-reported values are treated as authoritative unless a specific discrepancy is documented.
2. `000 MT` means thousand metric tonnes; ₹ crore and USD million retain their stated source scales.
3. Product-to-group mapping follows the project’s source/category definitions; LNG is excluded.
4. Month-over-month measures compare adjacent reported months only when both values are available.
5. Implied INR/USD and per-tonne values are calculated from aggregate reported import values and volumes. They are analytical ratios, not official exchange rates or transaction prices.
6. Indian Basket crude price is contextual and is not assumed to explain all import-value changes.
7. Forecast performance is assessed on the available August 2026 volume holdout. The 2-month moving average is a simple baseline, not a sophisticated forecasting model.
8. September–December baseline and scenarios are volume projections, not import-value or price forecasts.
9. Scenario adjustments use observed historical negative/positive monthly movements of 9.57% and 14.92%. Scenarios are planning estimates, not probability-based forecasts or statistical intervals.
10. Rounded figures in narrative tables may not sum exactly due to rounding.

## Limitations

- The observed period is only five months, limiting trend interpretation and forecast reliability.
- Only one holdout month is available for forecast comparison; 6.07% APE does not establish future accuracy.
- August INR/USD import values are unavailable, so August value trends and implied unit economics cannot be evaluated.
- Indian Basket is a crude benchmark and is not a direct measure of the price paid for the full petroleum import basket.
- Mix changes over April–August are descriptive and do not establish a structural shift.
- The upside/downside range reflects selected historical movements and does not quantify probabilities or all plausible outcomes.
- The documented export-row discrepancy is retained as a source validation note; export measures are outside project scope.

## Interpretation guidance

Use the August actual only for volume forecast validation. Use reported monetary values only for months in which they are present. Read implied ratios as aggregate indicators, and interpret the scenario range as a planning envelope that should be refreshed when additional actual data becomes available.

# Methodology

## Project scope

This project uses Microsoft Excel and Power Query to analyze Indian petroleum imports for April–August 2026 (FY 2026–27). The analytical scope is crude oil and petroleum products. LNG is excluded, and SQL is not used. Import-value comparisons cover April–July because August INR and USD values were unavailable in the validated value workbooks; August volume is used for forecast back-testing.

## Sources and data preparation

The inputs are PPAC historical import quantity, value-in-rupees, and value-in-dollars reports, plus PPAC’s Indian Basket crude-price series. Source files are organized by reporting period and category. Original reported values are retained; discrepancies are documented rather than silently overwritten.

Power Query is used to import, clean, normalize, and reshape source tables into a consistent month/product analytical structure. Month labels and sort order are standardized. Categories are mapped to crude or petroleum-product groups while retaining product-level detail. Numeric types and units are checked before calculations.

## Validation before analysis

Before joining or aggregating data, the workflow checks:

- Reporting month and fiscal-year alignment across source workbooks.
- Category/product alignment across quantity and value sources.
- Unit and scale consistency (thousand metric tonnes, ₹ crore, USD million, and USD/bbl as applicable).
- Product subtotals and reported import totals where comparable.
- Missing observations and arithmetic relationships.
- Differences between displayed detail rows and reported totals.

Any unresolved source difference is recorded with the affected measure and period. Missing values remain missing; they are not imputed for reporting.

## Analytical dataset and measures

The prepared table is organized at the available **month × product/category** grain. It carries source volume and monetary fields, group labels, month sorting, benchmark price context, and a status field for data availability. The accompanying `Data_Dictionary.xlsx` describes the documented fields and distinguishes source values from derived measures.

Derived measures include:

- **Total import volume:** sum of eligible crude and petroleum-product volume for a reporting month.
- **Group/product share:** category volume divided by monthly total volume.
- **Month-over-month change:** current month divided by prior month, less one, when both observations exist.
- **Implied INR per USD:** reported INR import value converted to ₹ crore divided by reported USD import value converted to USD million; the resulting scale is ₹ per USD.
- **Implied ₹ per tonne:** ₹ crore converted to rupees divided by thousand metric tonnes converted to tonnes.
- **Implied USD per tonne:** USD million converted to dollars divided by thousand metric tonnes converted to tonnes.

These aggregate ratios are indicators derived from reported trade values and quantity. They are not transaction-level prices, official exchange rates, or independent market quotes. August implied values are unavailable because August monetary source values are missing.

## Trend, contribution, and price-context analysis

Monthly total volume and reported values are reviewed separately. Mix analysis compares crude and petroleum-product shares. Product contribution analysis identifies which displayed product categories account for petroleum-product changes. The Indian Basket series is aligned by month and used as contextual market information. No causal effect is inferred from co-movement in this short observational series.

## Forecast comparison and selection

Three simple approaches are compared: two-month moving average, three-month moving average, and linear trend. August actual volume (21.73 M MT) is held out and compared with each method’s August prediction using absolute percentage error:

`APE = ABS(Forecast − Actual) / Actual × 100`

The two-month moving average had the lowest tested August APE: forecast 23.05 M MT and APE 6.07%. It is used as a short-term baseline. Because there is one holdout month and a short series, this selection is provisional rather than evidence of general predictive superiority.

The selected baseline is extended to September–December 2026, with a cumulative baseline of approximately 90.10 M MT. The forecast is a volume outlook only; it does not forecast import values or prices.

## Scenario construction

Downside and upside planning totals apply observed historical negative and positive monthly movement assumptions of 9.57% and 14.92% to the baseline, respectively. The resulting September–December totals are approximately 81.48 M MT downside, 90.10 M MT baseline, and 103.54 M MT upside. These are deterministic planning cases based on a very short history. They are not confidence intervals, prediction intervals, or probability estimates.

## Dashboard and communication

Validated outputs are summarized in an Excel dashboard covering import volume, import values where available, crude/product mix, product-level patterns, Indian Basket context, forecast, and scenarios. Labels identify units and unavailable observations. Findings are presented with the period and limitations needed to interpret them.

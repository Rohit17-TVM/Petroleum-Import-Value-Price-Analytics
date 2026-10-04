# Petroleum Import, Value & Price Analytics with Short-Term Forecast

**Data analyst portfolio project | Microsoft Excel | Power Query | Forecasting**

## Executive summary

This project analyzes India's petroleum import volume, reported import values, product mix, and Indian Basket crude-price context for April-August 2026 (FY 2026-27). The trade-value analysis covers April-July; August volume is used as a forecast holdout because August INR and USD import values were unavailable in the validated value workbooks.

Imports were volatile across the five observed months, and quantity did not always move with expenditure. In July, volume rose 7.98% while reported INR and USD import values fell 6.15% and 6.47%; implied import cost per tonne fell about 13.09%. Crude remained the dominant component, while the petroleum-product share rose from 8.57% in April to 12.51% in August. These five observations are descriptive and do not establish a structural change.

A two-month moving average was selected from the simple methods tested using August as a holdout. Its August forecast was 23.05 million tonnes against an actual 21.73 million tonnes (6.07% absolute percentage error). The September-December 2026 baseline totals approximately 90.10 million tonnes. Downside and upside planning scenarios total approximately 81.48-103.54 million tonnes. The scenario envelope is based on observed monthly movements, not a probability interval.

## Business problem

Petroleum import expenditure can change differently from import volume because of changes in product composition, realized import economics, benchmark prices, and currency effects. The project asks: **How did petroleum import volumes and values change, what product and price context accompanied those movements, and what does the recent volume pattern suggest for near-term planning?**

## Objectives and analytical questions

- Track monthly import volume and crude-versus-petroleum-product mix.
- Examine import values in INR and USD where reported; do they move proportionally with volume?
- Identify product categories contributing to petroleum-product movements.
- Compare aggregate import economics with Indian Basket crude prices without treating association as causation.
- Compare simple volume forecast approaches using the August holdout and produce a short-term baseline.
- Translate the baseline and observed volatility into planning scenarios and dashboard insights.

## Scope and tools

- **Period:** April-August 2026. Value analysis: April-July 2026.
- **Included:** crude oil and petroleum products; volume, reported import values, product categories, and Indian Basket price context.
- **Excluded:** LNG.
- **Tools:** Excel, Power Query, Excel formulas, analytical/pivot tables, charts, and dashboard.
- **SQL:** not used in this project.

## Methodology

1. Collect PPAC import quantity, INR-value, USD-value, and Indian Basket price series.
2. Validate periods, categories, units, totals/subtotals, missing observations, and arithmetic relationships. Preserve source values when discrepancies are found and document them.
3. Use Power Query to clean and reshape the inputs into an analysis-ready month/product structure.
4. Calculate total volume, mix shares, monthly changes, reported values, implied INR/USD, implied cost per tonne, and price context where source data permits.
5. Review product-level contributions and compare value and volume trends.
6. Back-test two-month moving average, three-month moving average, and linear trend against August actual volume; select the lowest August absolute percentage error as the baseline.
7. Extend the selected baseline to September-December and apply observed negative/positive monthly-movement assumptions for downside/upside planning scenarios.
8. Present the validated results in an Excel dashboard.

## Key findings

### Monthly import volume

| Month | Volume (million tonnes) |
|---|---:|
| April | 20.20 |
| May | 24.61 |
| June | 22.17 |
| July | 23.94 |
| August | 21.73 |

Volume fluctuated rather than following a steady upward trend. Crude share moved from approximately 91.43% in April to 87.49% in August; petroleum-product share moved from 8.57% to 12.51%. With five months of data, this is an observed mix change, not evidence of a durable structural shift.

### Volume and value diverged in July

July volume increased 7.98% month over month while INR import value decreased 6.15% and USD import value decreased 6.47%. Implied import cost per tonne declined approximately 13.09%. This supports monitoring volume, value, and implied unit cost together.

### Product and price context

LPG was the largest recurring petroleum-product import category among the highlighted categories; Petcoke rose materially in June, Fuel Oil was volatile, Naphtha declined significantly in July, and LOBS/Lube Oil was comparatively stable. Indian Basket crude price moved from $114.48/bbl in April to $89.31/bbl in August. The benchmark supplies context; this short series does not establish that it independently explains aggregate import value.

## Forecast and back-test

| Measure | Result |
|---|---:|
| Selected approach | Two-month moving average |
| August forecast | 23.05 M MT |
| August actual | 21.73 M MT |
| August absolute percentage error | 6.07% |
| September-December baseline total | 90.10 M MT |

The model was selected because it had the lowest August absolute percentage error among the three tested simple approaches. One holdout month is a narrow evaluation and does not establish consistent future superiority.

### Scenario planning range

| Scenario | Sep-Dec total (M MT) | Basis |
|---|---:|---|
| Downside | 81.48 | Baseline adjusted by observed downside movement of 9.57% |
| Baseline | 90.10 | Selected two-month moving-average approach |
| Upside | 103.54 | Baseline adjusted by observed upside movement of 14.92% |

These are planning estimates derived from the limited observed history, not statistical confidence intervals or probability-weighted forecasts.

## Data sources

- [PPAC historical import/export reports](https://ppac.gov.in/import-export/history) - separate quantity, value-in-rupees, and value-in-dollars reports.
- [PPAC international crude prices (Indian Basket)](https://ppac.gov.in/prices/international-prices-of-crude-oil) - benchmark price context.

The source files and their retrieval/version details should be retained with the analysis workbook when publishing the project. PPAC data may be revised after retrieval.

## Validation and data limitations

- Quantity, INR-value, and USD-value sources were checked for period/category alignment, unit consistency, totals, subtotals, missing values, and arithmetic relationships.
- A discrepancy was identified between reported total product export values and the sum of displayed product-export rows for April-July 2026. The reported source total was retained and the discrepancy documented. This is an export-side source validation note; exports are outside the analytical scope.
- August import volume is available, but August INR/USD import values were not available in the validated value workbooks. No August monetary values were estimated.
- Forecast validation uses one holdout month; the historical window is short.
- Implied unit costs and exchange rates are ratios of reported aggregate values and volumes, not quoted transaction prices or independent FX observations.
- Indian Basket is a benchmark/context variable. The analysis does not claim causation.

## Business recommendations

1. Monitor volume, reported import value, and implied cost per tonne together.
2. Track product-level drivers such as LPG, Petcoke, Fuel Oil, Naphtha, and LOBS/Lube Oil alongside aggregate product imports.
3. Review crude and petroleum-product shares monthly; treat the observed five-month change as a monitoring signal, not a confirmed structural shift.
4. Use Indian Basket price alongside mix, volume, unit economics, and currency context rather than as a standalone import-bill predictor.
5. Use the 90.10 M MT baseline and 81.48-103.54 M MT scenario envelope as short-term planning references, updating them as actuals arrive.

## Conclusion

The analysis shows why petroleum import monitoring should combine quantities, reported values, product composition, and price context. July demonstrates that volume and expenditure can diverge. The Excel/Power Query workflow produces a documented, validated dashboard and a transparent short-term baseline, while the brief history and single-month back-test call for cautious interpretation.

## Repository contents

```text
Petroleum-Import-Value-Price-Analytics/
│
├── README.md
│
├── analysis/
│   └── Petroleum_Import_Value_Price_Analytics.xlsx
│
├── documentation/
│   ├── Data_Dictionary.xlsx
│   ├── Methodology.md
│   └── Validation_and_Assumptions.md
│
├── data/
│   └── processed/
│       └── Petroleum_Master_Validated.xlsx
│
└── images/
    ├── dashboard_overview.png
    ├── product_analysis.png
    └── forecast_analysis.png
```

The repository contains the analysis workbook, validated processed dataset, supporting documentation, and selected dashboard images in the structure shown above.
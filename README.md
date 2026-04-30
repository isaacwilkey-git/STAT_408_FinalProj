# Obesity in America
### Patterns in Nutrition, Physical Activity & Weight Status Across the United States
**STAT 408 Final Project — Isaac Wilkey**

---

## Overview

This project investigates patterns in adult obesity, physical activity, and diet across the United States using CDC behavioral surveillance data. The analysis explores geographic variation, trends over time, behavioral predictors, and demographic disparities in obesity prevalence.

The deliverable is an interactive **Quarto dashboard** (`obesity_dashboard.qmd`) that renders to HTML with four pages mirroring the project's narrative structure.

---

## Data Source

**Nutrition, Physical Activity, and Obesity – Behavioral Risk Factor Surveillance System (BRFSS)**
- **Provider:** Centers for Disease Control and Prevention (CDC) — [DNPAO Data, Trends & Maps](https://www.cdc.gov/nccdphp/dnpao/data-trends-maps/index.html)
- **Population:** U.S. adults aged 18 and older
- **Geography:** All 50 states and U.S. territories
- **File:** `STAT_408_Final_proj_data.csv` *(place in the project root before rendering)*

---

## Dashboard Pages

| Page | Contents |
|---|---|
| **Dataset** | Data source overview, key variables, and dataset dimensions |
| **Data Cleaning** | Step-by-step cleaning pipeline with rows-removed tracker |
| **Analysis** | Tabbed charts — bar chart, choropleth map, trend line, scatter plot |
| **Findings** | Key takeaways, income disparity chart, and further resources |

---

## Data Cleaning Steps

1. **Type conversion** — stripped commas and coerced `Sample_Size` and `Data_Value` to numeric
2. **Blank → NA** — replaced empty strings with `NA` for consistent missing-value handling
3. **Remove flagged values** — dropped rows where `Data_Value_Footnote` was not `NA` (suppressed/unreliable CDC estimates)
4. **Remove missing outcomes** — filtered out rows with no `Data_Value`
5. **Drop unused columns** — removed `Data_Value_Type`, `Data_Value_Unit`, and two other metadata columns

---

## Key Findings

- **Geographic clustering** — Southeastern states (led by West Virginia and Mississippi) consistently show the highest obesity rates; Western states rank lowest
- **Rising trend** — National average obesity rose nearly 5 percentage points over the study period with no sign of leveling off
- **Activity correlation** — States with higher physical activity rates have meaningfully lower obesity prevalence (r ≈ −0.70)
- **Income gradient** — Adults in the lowest income bracket face obesity rates nearly 10 points higher than the highest earners

---

## Requirements

```r
install.packages(c("tidyverse", "maps", "ggrepel"))
```

- [Quarto](https://quarto.org/docs/get-started/) (v1.4 or later recommended for dashboard format)
- R (v4.1+)

---

## Rendering

Place `STAT_408_Final_proj_data.csv` in the same directory as `obesity_dashboard.qmd`, then run:

```bash
quarto render obesity_dashboard.qmd
```

This will produce `obesity_dashboard.html` which can be opened in any browser.

---

## Project Structure

```
.
├── obesity_dashboard.qmd         # Quarto dashboard source
├── STAT_408_Final_proj_data.csv  # CDC BRFSS data (required)
└── README.md
```

---

## Further Resources

- [America's Health Rankings — Obesity](https://www.americashealthrankings.org/explore/measures/Obesity)
- [CDC DNPAO Data Portal](https://www.cdc.gov/nccdphp/dnpao/data-trends-maps)
- [CDC BRFSS Overview](https://www.cdc.gov/brfss)
- [Healthy People 2030 — Obesity](https://health.gov/healthypeople/objectives-and-data/browse-objectives/obesity)

# Obesity in America: Patterns in Nutrition, Physical Activity & Weight Status

**STAT 408 Final Project** | Isaac Wilkey

An analysis of adult obesity prevalence across the United States using CDC behavioral surveillance data. This project explores geographic variation, time trends, demographic disparities, and the relationship between physical activity and obesity rates.

---

## Data

**Source:** [CDC DNPAO Data, Trends, and Maps](https://www.cdc.gov/obesity/data/index.html) — Nutrition, Physical Activity, and Obesity Behavioral Risk Factor Surveillance System (BRFSS)

The dataset contains population-level estimates of adult diet, physical activity, and weight status across all U.S. states, with demographic breakdowns by age, sex, income, education, and race/ethnicity.

**File:** `STAT_408_Final_proj_data.csv` *(place in project root before rendering)*

---

## Project Structure

```
├── obesity_presentation.qmd   # Quarto Revealjs presentation
├── styles.css                 # Custom slide styles
├── STAT_408_Final_proj_data.csv
└── README.md
```

---

## Research Questions

1. How do obesity rates vary by state?
2. How has the national average obesity rate trended over time?
3. Is there a relationship between physical activity rates and obesity prevalence?
4. How do obesity rates differ across demographic groups (age, income, sex, education)?

---

## Key Findings

- **Geographic clustering:** Southeastern states consistently show the highest obesity rates, with West Virginia (37.9%) and Mississippi (37.1%) at the top. Western states rank lowest.
- **Rising trend:** The national average increased by nearly 5 percentage points over the study period with no year showing a decline.
- **Activity predicts obesity:** States with higher physical activity compliance rates tend to have lower obesity prevalence (r ≈ −0.70).
- **Income gradient:** Adults in the lowest income bracket face obesity rates nearly 10 points higher than the highest earners.

---

## Rendering the Presentation

Install [Quarto](https://quarto.org/docs/get-started/) and the required R packages, then run:

```bash
quarto render obesity_presentation.qmd
```

**Required R packages:**

```r
install.packages(c("tidyverse", "maps", "ggrepel"))
```

---

## Additional Resources

- [America's Health Rankings – Obesity](https://www.americashealthrankings.org/explore/measures/Obesity)
- [CDC DNPAO Data Portal](https://www.cdc.gov/obesity/data/index.html)

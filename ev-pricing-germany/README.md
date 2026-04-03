# EV Pricing in Germany
**Assessing the Impact of Energy Efficiency on Electric Vehicle Pricing**
`UC Berkeley · Dec 2023`

---

## Overview

Modeled the relationship between energy efficiency and pricing across 308 EV models 
available in Germany using multiple linear regression with log transformations.

**Research Question:** What is the effect of energy efficiency (Wh/km) on EV cost 
in Germany, and how is this impacted by acceleration, range, and drivetrain?

---

## 📂 Contents

| File | Description |
|------|-------------|
| `ev-pricing-germany.Rmd` | R Markdown analysis file |
| `ev-pricing-germany.pdf` | Full research report |

---

## Key Results

- **R² = 0.764** — model explains ~76.4% of variability in EV pricing
- A 1% increase in efficiency → **1.55% increase** in price
- A 1% decrease in acceleration time → **0.77% decrease** in price
- A 1% increase in range → **0.38% increase** in price
- Addressed multicollinearity, omitted variable bias, and reverse causality

[Full Report](./ev-pricing-germany.pdf)

---

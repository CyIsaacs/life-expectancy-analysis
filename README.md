# life-expectancy-analysis
Regression analysis of life expectancy using WHO/UN data (193 countries, 2000–2015) data cleaning, EDA, and multiple linear regression in Python


# Life Expectancy Analysis (WHO Dataset)

Exploratory data analysis and regression modelling investigating how economic,
demographic, and health factors relate to life expectancy across 193 countries
(2000–2015).

## Data

Source: [Life Expectancy (WHO)](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who),
Kaggle, originally collected from the WHO and UN.

193 countries, 2000–2015, 22 variables covering mortality, immunization,
economic indicators (GDP, expenditure), and social factors (schooling, income
composition).

## Methods

- **Data cleaning:** column name standardization, missingness analysis
  (overall and by development status), two-stage imputation (within-country
  median, then column median for any remainder), log transformation of
  right-skewed variables (GDP, population, infant deaths, measles, etc.)
- **EDA:** summary statistics (mean, spread, skew, kurtosis), univariate
  distributions, violin/histogram comparisons by country status, correlation
  heatmap, bivariate scatter plots against life expectancy, and a time-series
  view of life expectancy trends (2000–2015)
- **Modelling:** simple linear regression (life expectancy ~ HIV/AIDS
  prevalence) as a baseline, followed by three multiple linear regression
  specifications testing different sets of economic, health-system, and
  social predictors
- **Diagnostics:** residuals vs. fitted, normal Q-Q, scale-location, and
  Cook's distance plots to check linearity, normality, homoscedasticity, and
  influential observations

## Key findings

- Life expectancy is most strongly associated with **HIV/AIDS prevalence**
  and **adult mortality** (negative), and with **schooling** and **income
  composition of resources** (positive) — consistent across correlation
  analysis and all three regression models.
- Developed and developing countries show clearly different life expectancy
  distributions, though the gap has narrowed over 2000–2015 as developing
  countries improved faster on average.
- The missingness in the data is not random — it concentrates in variables
  like GDP, immunization coverage, and health expenditure, and skews toward
  developing countries, suggesting missingness is tied to reporting capacity
  rather than chance.
- The best-performing model combined HIV/AIDS prevalence, schooling, adult
  mortality, income composition of resources, and development status
  (adjusted R² = 0.82), balancing explanatory power with interpretability.
- Residual diagnostics broadly support the linear model (residuals centered
  around zero, no high-leverage outliers by Cook's distance) with mild
  non-normality in the tails, likely reflecting the diversity of countries
  in the sample.

## Tools

Python · pandas · numpy · statsmodels · seaborn · matplotlib

---
*This is coursework for PSTAT 100 (Data Science Concepts and Analysis) at UC
Santa Barbara. Shared for portfolio purposes.*

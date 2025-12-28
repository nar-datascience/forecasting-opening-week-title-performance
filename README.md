[README-forecasting-netflix-titles.md](https://github.com/user-attachments/files/24357738/README-forecasting-netflix-titles.md)
# Forecasting Opening Week Viewership for Netflix Titles

## Project Overview
This project builds a machine learning model to predict opening week member hours for new Netflix titles scheduled for release in 2025. Using synthetic historical release data from 2019–2024, the model estimates early viewership performance to support content planning, marketing allocation, and release strategy decisions.

A regularized linear regression approach is used, with performance evaluated against simple genre-based heuristics.

---

## Business Problem
Opening week performance is a critical success indicator for streaming content, influencing marketing spend, homepage placement, and long-term investment decisions.

The objective of this project is to:

1. Accurately predict opening week viewership for upcoming titles
2. Improve upon baseline heuristics based on average genre performance
3. Identify the most influential factors driving early audience engagement

This enables data-driven decisions around marketing investment, content positioning, and release timing.

---

## Data Description
- **Titles:** 2,525 releases (2019–2025)
- **Target Variable:** Opening week viewership (in millions of member hours)
- **Features:** 31 raw features before preprocessing, 66 features after encoding and transformation

The dataset includes information related to genre, marketing, competition, release timing, and content characteristics.

---

## Methodology

**Data Cleaning:**

- Removed duplicate observations
- Corrected inconsistent data types and formats
- Addressed missing values using:
  - Iterative regression-based imputation
  - Distribution-based imputation
  - Random sample imputation
  - Creation of new categorical levels where appropriate

**Feature Engineering:**

- One-hot, ordinal, and cyclical encoding for categorical variables
- Log transformations applied to log-normal features
- Box–Cox transformation applied to the target variable
- Assessed skewness and multicollinearity to support linear modeling assumptions

**Modeling Approach:**

- Established a baseline heuristic using average opening week viewership by genre
- Trained and evaluated regularized linear models using cross-validation
- Performed hyperparameter tuning to select optimal regularization strength
- Compared models using MAE, RMSE, and MAPE

---

## Key Insights
**Baseline Heuristic Performance:**

- MAE: 7.889
- RMSE: 9.748
- MAPE: 26.98%

**Ridge Regression Performance:**

- MAE: 6.329
- RMSE: 8.125
- MAPE: 22.03%

The Ridge model significantly outperformed the baseline and demonstrated strong generalization with no evidence of overfitting or underfitting.

**Most Important Features:**

1. Marketing spend
2. Whether the title is based on a known IP
3. Number of competing titles released within ±2 weeks
4. Homepage hero share
5. Primary genre = Drama

Competition density and drama classification showed a negative correlation with opening week viewership, while marketing spend, known IP, and homepage hero share showed a positive correlation.

## Recommendations

- Increase marketing spend for high-priority releases
- Allocate more homepage hero exposure during launch windows
- Reduce the number of competing releases within short time frames
- Prioritize content based on established IP
- Be cautious with drama titles, which underperform on average in opening week engagement

---

## Tools & Technologies
- **Python**
- **pandas**, **NumPy** – data manipulation  
- **matplotlib**, **seaborn** – visualization  
- **scikit-learn** – regression models  
- **Jupyter Notebook** – analysis and documentation  

---

## Repository Structure
```
├── Forecasting Opening Week Member Hours for New Netflix Titles - summary.pdf
├── Forecasting Opening-Week Member-Hours for New Netflix Titles.ipynb
├── netflix_opening_week_data_dictionary.csv
├── netflix_opening_week_dataset.csv
├── README.md
```

---

## Next Steps

- Explore non-linear models (e.g., gradient boosting) for comparison
- Segment predictions by region or audience demographic

---

## Contact
If you’d like to discuss this project or explore related work, feel free to connect with me on LinkedIn or view my other repositories.


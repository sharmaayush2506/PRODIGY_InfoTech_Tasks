# Task 2 — Data Cleaning & Exploratory Data Analysis

## Objective
Perform data cleaning and exploratory data analysis (EDA) on the Titanic 
dataset. Explore relationships between variables and identify patterns 
and trends in the data.

## Dataset
Titanic Dataset (Kaggle) — passenger demographics and survival outcomes 
from the Titanic disaster.

## Approach
- Checked and handled missing values (Age filled with median, Embarked 
  filled with mode, Cabin dropped due to ~77% missing data)
- Explored survival rate by gender and passenger class
- Visualized age distribution across survival outcomes using boxplots
- Built a correlation heatmap across numeric variables
- Engineered a FamilySize feature (SibSp + Parch + 1) to explore family 
  size vs survival

## Tools Used
Python, Pandas, Matplotlib, Seaborn

## Key Insight
Gender and passenger class (proxied by Fare) were the strongest predictors 
of survival, while age had minimal standalone impact. Women in every class 
survived at notably higher rates than men, and wealthier/higher-class 
passengers had a clear survival advantage over 3rd class passengers.

## Files
- `task2.ipynb` — full code, cleaning steps, and visualizations
- `datsets/` — Titanic dataset used
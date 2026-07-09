# Titanic Exploratory Data Analysis

A mini exploratory data analysis (EDA) on the classic Titanic dataset, focused on data cleaning, groupby-based survival analysis, and visual storytelling.

## Overview

This project investigates what factors were associated with passenger survival aboard the Titanic. It goes beyond basic summary statistics by cleaning the raw data, engineering new features, and using `groupby` aggregations to answer specific survival-rate questions, all backed by supporting visualizations.

**Key questions explored:**
- How did survival rate vary by age group?
- How did survival rate vary by embarkation port?
- How did survival rate vary by family size (siblings/spouses + parents/children)?

## Dataset

The analysis uses `train.csv`, the standard Titanic training dataset (891 passengers, 12 features), including:

| Column | Description |
|---|---|
| `Survived` | Survival (0 = No, 1 = Yes) |
| `Pclass` | Ticket class (1st, 2nd, 3rd) |
| `Sex`, `Age` | Passenger demographics |
| `SibSp`, `Parch` | Siblings/spouses and parents/children aboard |
| `Fare`, `Cabin`, `Embarked` | Ticket fare, cabin, and port of embarkation |

## Methodology

1. **Data understanding** — inspected shape, dtypes, and summary statistics
2. **Data cleaning**
   - Imputed missing `Age` values
   - Filled missing `Embarked` values with the mode
   - Dropped the `Cabin` column (~77% missing)
3. **Feature engineering**
   - Binned `Age` into groups (Child, Teen, Young Adult, Adult, Senior)
   - Created `FamilySize` from `SibSp + Parch`
4. **Analysis** — `groupby` aggregations to compute survival rate by age group, embarkation port, and family size
5. **Visualization**
   - Age distribution histogram
   - Correlation heatmap (with `Sex` encoded numerically)
   - Bar plots of survival rate by age group, embarkation port, and family size

## Key Findings

- **Age**: Children had the highest survival rate; seniors had the lowest.
- **Embarkation port**: Passengers who boarded at Cherbourg survived at a notably higher rate than those from Southampton or Queenstown.
- **Family size**: Small families (1–3 members) had the best survival outcomes; solo travelers and large families (4+) fared worse.
- **Correlations**: `Sex`, `Pclass`, and `Fare` showed the strongest relationships with survival.

## Repository Structure

```
.
├── Task3_Titanic_EDA.ipynb   # Jupyter notebook with full analysis
├── train.csv                 # Titanic dataset
└── README.md                 # Project documentation
```

## Tech Stack

- Python 3
- pandas, numpy
- matplotlib, seaborn
- Jupyter Notebook

## Getting Started

**Clone the repository:**
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

**Install dependencies:**
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

**Run the notebook:**
```bash
jupyter notebook Task3_Titanic_EDA.ipynb
```

## Author

Preethi Ann
Data Science/Analysis with Python Internship

## Acknowledgments

Dataset sourced from the well-known [Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic) competition.


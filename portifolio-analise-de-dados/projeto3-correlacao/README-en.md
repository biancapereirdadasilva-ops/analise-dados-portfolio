markdown
# Correlation of Categorical Variables with Cramér's V

## About
This project implements **Cramér's V** coefficient to measure the strength of association between two categorical variables.

## Why Cramér's V?
- Pearson correlation works only for **numeric** data
- For categorical variables (like race, gender, education level), we use **Cramér's V**
- Result ranges from **0 to 1**:
  - 0 = no association
  - 1 = perfect association

## Function Implementation

python
def cramer_v(col1, col2):
    contingency_table = pd.crosstab(col1, col2)
    chi2 = chi2_contingency(contingency_table)[0]
    n = contingency_table.sum().sum()
    min_dim = min(contingency_table.shape) - 1
    return np.sqrt(chi2 / (n * min_dim))

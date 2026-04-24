
# Handling Missing Values with Pandas

## About
This project demonstrates strategies to identify and handle missing values (NaN) in datasets using Pandas.

## Concepts Applied
- Null detection with `.isnull().sum()`
- Filling with `.fillna()` and `.loc[]`
- Using median for data with outliers
- Conditional filling based on auxiliary column

## Practical Example

```python
# Checking null values
data['SALARY'].isnull().sum()  # 577 null values

# Filling with median
median_salary = data['SALARY'].median()
data.loc[data['SALARY'].isnull(), 'SALARY'] = median_salary

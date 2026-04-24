
markdown
# Feature Engineering with Python

## About
This project demonstrates **feature engineering** techniques - creating new variables from existing data, an essential step for improving analysis and preparing data for machine learning.

## What is Feature Engineering?
It's the process of transforming raw data into **features** (variables) that facilitate analysis and improve predictive model performance.

## Techniques Demonstrated

### 1. Conditional Variable Creation
python
def fill_level(manager, level):
    if manager == 1:
        return "Manager"
    return level

data['NEW_LEVEL'] = data.apply(
    lambda x: fill_level(x['MANAGER?'], x['LEVEL']), axis=1
)

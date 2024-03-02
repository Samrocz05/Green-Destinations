## Analysis of Attrition at Green Destinations Travel Agency

This repository contains code for analyzing employee attrition at Green Destinations Travel Agency.

### Analysis

1. **Attrition Rate Calculation**: The code calculates the attrition rate, which is the percentage of employees who have left the company.

2. **Exploring Factors**: It explores the relationship between attrition and factors such as age, years at the company, and income.

3. **Data Visualization**: The analysis includes visualizations using Matplotlib and Seaborn to understand the distribution of age, years at the company, and monthly income among employees who left versus those who stayed.

### Usage

To use this code:
1. Clone this repository.
2. Ensure you have Python, Pandas, Matplotlib, and Seaborn installed.
3. Replace `"green_destinations_employee_data.csv"` with the actual file path of your dataset.
4. Run the Jupyter Notebook or Python script to perform the analysis.

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

data = pd.read_csv("green_destinations_employee_data.csv")

attrition_rate = (data['Attrition'].value_counts(normalize=True) * 100)['Yes']
print(f"Attrition Rate: {attrition_rate:.2f}%")

# Explore relationship between attrition and factors like age, years at the company, and income
attrition_factors = ['Age', 'YearsAtCompany', 'MonthlyIncome']
for factor in attrition_factors:
    print(f"\nAverage {factor} for employees who left vs. those who stayed:")
    print(data.groupby('Attrition')[factor].mean())

plt.figure(figsize=(15, 5))
# Visualization code goes here...
plt.show()
```

### License

This project is licensed under the [MIT License](LICENSE).

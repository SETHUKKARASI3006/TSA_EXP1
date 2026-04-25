# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 20.04.2026

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity/temperature).
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.

# PROGRAM:

```
import matplotlib.pyplot as plt
import pandas as pd
df = pd.read_csv("/education_vs_income_econometrics_samples.csv")
df.head()
df.dtypes
df.set_index('x_education_years',inplace=True)
df_unique_index = df.groupby(level=0)['y_income_thousands_usd'].mean()
idx_full = pd.Index(range(df_unique_index.index.min(), df_unique_index.index.max() + 1), name='x_education_years')
df_resample = df_unique_index.reindex(idx_full).interpolate()
df_resample.plot(kind='line', label = 'Total Salary', color = 'blue')
plt.title('Time Series plot of Salary based on number of years of education')
plt.xlabel('Number of years')
plt.ylabel('Salary(in USD)')
plt.legend()
plt.grid(True)
plt.show()
```

# OUTPUT:

<img width="591" height="239" alt="image" src="https://github.com/user-attachments/assets/a35aaa67-cfc6-4677-bc78-3a525cb60f12" />

<img width="397" height="246" alt="image" src="https://github.com/user-attachments/assets/96c99bfb-5062-4725-afcc-1e722c8e17b0" />

<img width="587" height="455" alt="image" src="https://github.com/user-attachments/assets/16f487bf-b744-4839-b282-197383b50e76" />


# RESULT:
Thus we have created the python code for plotting the time series of given data.

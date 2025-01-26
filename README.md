# Python Examples for Data Analysis and Visualization

This document contains examples showcasing the use of Python libraries such as `pandas`, `matplotlib`, `numpy`, `plotly`, and statistical methods for data manipulation, visualization, and analysis. Below is the explanation for each example.

---

### Example 1: Creating a DataFrame
```python
import pandas as pd
dis = {
    "name": ['sadman', 'bushra', 'kabir'],
    "roll": ['10', '20', '30'],
    "area": ['a', 'b', 'c']
}
s = pd.DataFrame(dis)
s
```
Creates a simple DataFrame with columns `name`, `roll`, and `area`.

---

### Example 2: Save DataFrame to CSV
```python
s.to_csv('friends.csv')
```
Saves the DataFrame to a file named `friends.csv`.

---

### Example 3: Save DataFrame to CSV Without Index
```python
s.to_csv('friends_noindex.csv', index=False)
```
Saves the DataFrame to a CSV file without including the index.

---

### Example 4: Display First 2 Rows
```python
s.head(2)
```
Displays the first two rows of the DataFrame.

---

### Example 5: Display Last 2 Rows
```python
s.tail(2)
```
Displays the last two rows of the DataFrame.

---

### Example 6: Generate Descriptive Statistics
```python
s.describe()
```
Provides descriptive statistics for numerical columns in the DataFrame.

---

### Example 7: Reading a CSV File
```python
a = pd.read_csv('new_file.csv')
a
```
Reads data from `new_file.csv` into a DataFrame.

---

### Example 8: Creating a Series
```python
import pandas as pd
data = [1, 2, 3, 4]
series = pd.Series(data, index=['a', 'b', 'c', 'd'])
print(series)
```
Creates a pandas Series with custom indices.

---

### Example 9: Handling Missing Values
```python
import pandas as pd
import numpy as np
dis = {
    "name": ['sadman', 'bushra', 'kabir', 'catto'],
    "roll": ['10', '20', np.nan, '30'],
    "area": ['a', np.nan, 'b', 'c']
}
s = pd.DataFrame(dis)
s
```
Demonstrates missing values in a DataFrame.

---

### Example 10: Filling Missing Values
```python
d_filled = s.fillna({'roll': s['roll'].mean(), 'area': 'unknown'})
d_filled
```
Fills missing values with column-specific defaults.

---

### Example 11: Removing Duplicates and Missing Values
```python
no_duplicates = s.drop_duplicates()
missing = s.isnull()
d_dropped = s.dropna()
```
Shows how to remove duplicates and handle missing values.

---

### Example 12: Merging DataFrames by Key
```python
df1 = pd.DataFrame({
    'id': [1, 2, 3, 4],
    'name': ['sadman', 'bushra', 'afaf', 'adaf']
})
df2 = pd.DataFrame({
    'id': [1, 2, 3, 4],
    'roll': [34, 4235, 2421, 124]
})
merged = pd.merge(df1, df2, on='id')
merged
```
Merges two DataFrames using a common column.

---

### Example 13: Merging DataFrames with Different Keys
```python
merged = pd.merge(df1, df2, left_on='id', right_on='idol')
merged
```
Merges DataFrames using different key columns.

---

### Example 14: Sorting a DataFrame
```python
sorting = df.sort_values(by='roll')
```
Sorts the DataFrame by the `roll` column.

---

### Example 15: Filtering Data
```python
filtered = df[df['roll'] > 2]
print(filtered)
```
Filters rows where the `roll` value is greater than 2.

---

### Example 16: Grouping Data and Summing
```python
grouped_data = df.groupby('catagory').sum()
grouped_data
```
Groups data by `catagory` and calculates the sum for each group.

---

### Example 17: Applying Custom Aggregation
```python
def sales_range(x):
    return x.max() - x.min()
grouped_data = df.groupby('catagory').agg({'sales': sales_range})
```
Applies a custom aggregation function to grouped data.

---

### Example 18-23: Plotting with Matplotlib
Demonstrates different types of plots, including line plots, scatter plots, and bar charts, using `matplotlib`.

#### Example 18-19: Line Plot
```python
p.plot(years, sales, marker='o', linestyle='-', color='blue', linewidth=2)
```
Plots a line chart with markers.

#### Example 20: Scatter Plot
```python
p.scatter(years, sales, color='blue')
```
Creates a scatter plot.

#### Example 23: Bar Chart with Grid
```python
p.bar(years, sales, color='purple', linewidth=0.5, edgecolor='black')
```
Generates a bar chart with a grid.

---

### Example 24: Subplots
```python
fig, (ax1, ax2) = p.subplots(1, 2)
ax1.plot(x, y1, color='blue')
ax2.plot(x, y2, color='green')
```
Creates multiple plots in one figure.

---

### Example 25: Interactive Plot with Plotly
```python
import plotly.graph_objects as go
fig = go.Figure(data=go.Scatter(x=months, y=sales, mode='lines+markers'))
fig.show()
```
Generates an interactive line plot using Plotly.

---

### Example 26-28: Statistical Measures
Demonstrates mean, median, variance, and standard deviation calculations using pandas.

#### Example 26: Mean, Median, and Mode
```python
print(f"Mean: {dfmean}")
print(f"Median: {dfmedian}")
print(f"Mode: {dfmode[0]}")
```

#### Example 28: Range, Variance, and Standard Deviation
```python
range_value = df['score'].max() - df['score'].min()
print(f"Range: {range_value}")
```

---

### Example 29: Histogram
```python
plt.hist(data, bins=30, density=True, alpha=0.7, color='blue')
```
Creates a histogram for normally distributed data.

---

### Example 30-31: Probability Distributions
Demonstrates binomial and Poisson distributions using `scipy.stats`.

#### Example 30: Binomial Distribution
```python
probabilities = binom.pmf(x, n, p)
plt.bar(x, probabilities, color='green')
```

#### Example 31: Poisson Distribution
```python
probabilities = poisson.pmf(x, lmda_pram)
plt.bar(x, probabilities, color='purple')
```

---


---
share: true
---

# Comprehensive Data Science Libraries Cheatsheet

## Pandas for Data Manipulation

### Data Structures

- `pd.Series(data, index)`: Create a Series.
```python
import pandas as pd

data = [1, 2, 3, 4, 5]
index = ['a', 'b', 'c', 'd', 'e']
series = pd.Series(data, index=index)
```
- `pd.DataFrame(data, index, columns)`: Create a DataFrame.
```python
import pandas as pd

data = {'Name': ['Alice', 'Bob', 'Charlie'],
        'Age': [25, 30, 22]}
index = [1, 2, 3]
columns = ['Name', 'Age']
df = pd.DataFrame(data, index=index, columns=columns)
```

### Data Loading and Inspection

- `df.head()`, `df.tail()`: View first/last rows.
```python
df.head()  # Display first 5 rows
df.tail(3)  # Display last 3 rows
```
- `df.info()`: Summary of DataFrame.
```python
df.info()
```
- `df.describe()`: Descriptive statistics.
```python
df.describe()
```
- `df.shape`: Number of rows and columns.
```python
rows, cols = df.shape
```
- `df.columns`, `df.index`: Access columns and index.
```python
columns = df.columns
index = df.index
```

### Data Selection and Manipulation

- `df['column']`, `df[['col1', 'col2']]`: Access columns.
```python
column_values = df['column']
subset = df[['col1', 'col2']]
```
- `df.loc[row_indexer, col_indexer]`: Label-based indexing.
```python
value = df.loc[2, 'column']
subset = df.loc[:, ['col1', 'col2']]
```
- `df.iloc[row_indexer, col_indexer]`: Integer-based indexing.
```python
value = df.iloc[0, 1]
subset = df.iloc[1:3, 0:2]
```
- `df.query('condition')`: Filter rows using query.
```python
filtered_df = df.query('Age > 25')
```
- `df.drop(columns=['col1'])`: Drop columns.
```python
df.drop(columns=['Age'], inplace=True)
```
- `df.drop(index=[row_index])`: Drop rows.
```python
df.drop(index=[1, 3], inplace=True)
```
- `df.rename(columns={'old_name': 'new_name'})`: Rename columns.
```python
df.rename(columns={'Name': 'Full Name'}, inplace=True)
```
- `df.sort_values(by='column')`: Sort rows.
```python
sorted_df = df.sort_values(by='Age', ascending=False)
```
- `df.groupby('column').agg(func)`: Group and aggregate.
```python
grouped = df.groupby('City').agg({'Age': 'mean', 'Salary': 'sum'})
```

### Data Cleaning

- `df.drop_duplicates()`: Remove duplicates.
```python
cleaned_df = df.drop_duplicates()
```
- `df.fillna(value)`: Fill missing values.
```python
filled_df = df.fillna(0)
```
- `df.dropna()`: Remove rows with missing values.
```python
cleaned_df = df.dropna()

## NumPy for Numerical Operations

### Basics

- `import numpy as np`: Import NumPy.
```python
import numpy as np
```
- `np.array([data])`: Create a NumPy array.
```python
array = np.array([1, 2, 3, 4, 5])
```
- `array.shape`: Shape of the array.
```python
shape = array.shape
```
- `array.ndim`: Number of dimensions.
```python
ndim = array.ndim
```
- `array.dtype`: Data type of elements.
```python
dtype = array.dtype
```

### Array Manipulation

- `np.reshape(array, new_shape)`: Reshape array.
```python
reshaped_array = np.reshape(array, (2, 3))
```
- `np.concatenate(arrays, axis)`: Concatenate arrays.
```python
concatenated = np.concatenate([array1, array2], axis=0)
```
- `np.split(array, indices_or_sections)`: Split array.
```python
split_arrays = np.split(array, 2)
```
- `np.vstack(array1, array2)`: Vertically stack arrays.
```python
stacked_vertically = np.vstack([array1, array2])
```
- `np.hstack(array1, array2)`: Horizontally stack arrays.
```python
stacked_horizontally = np.hstack([array1, array2])
```

### Numerical Operations

- `np.mean(array)`, `np.median(array)`: Mean, median.
```python
mean = np.mean(array)
median = np.median(array)
```
- `np.min(array)`, `np.max(array)`: Minimum, maximum.
```python
minimum = np.min(array)
maximum = np.max(array)
```
- `np.std(array)`, `np.var(array)`: Standard deviation, variance.
```python
std_dev = np.std(array)
variance = np.var(array)
```
- `np.sum(array)`: Sum of array elements.


```python
sum_array = np.sum(array)

## Matplotlib and Seaborn for Data Visualization

### Matplotlib

- `import matplotlib.pyplot as plt`: Import Matplotlib.
```python
import matplotlib.pyplot as plt
```
- Line Plot: `plt.plot(x, y)`.
```python
x = [1, 2, 3, 4, 5]
y = [10, 20, 15, 30, 25]
plt.plot(x, y)
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Line Plot')
plt.show()
```
- Scatter Plot: `plt.scatter(x, y)`.
```python
plt.scatter(x, y, color='blue', marker='o', label='Data Points')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Scatter Plot')
plt.legend()
plt.show()
```
- Bar Plot: `plt.bar(x, y)`.
```python
x = ['A', 'B', 'C']
y = [15, 25, 10]
plt.bar(x, y, color='green')
plt.xlabel('Categories')
plt.ylabel('Values')
plt.title('Bar Plot')
plt.show()
```
- Histogram: `plt.hist(data, bins)`.
```python
data = [2, 3, 3, 4, 4, 4, 5, 5, 5, 5]
plt.hist(data, bins=3, edgecolor='black')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.title('Histogram')
plt.show()
```
- Pie Chart: `plt.pie(data, labels)`.
```python
data = [30, 40, 20, 10]
labels = ['A', 'B', 'C', 'D']
plt.pie(data, labels=labels, autopct='%1.1f%%', startangle=90)
plt.title('Pie Chart')
plt.show()
```

### Seaborn

- `import seaborn as sns`: Import Seaborn.
```python
import seaborn as sns
```
- Scatter Plot: `sns.scatterplot(x, y, data)`.
```python
sns.scatterplot(x='Age', y='Salary', data=df)
plt.xlabel('Age')
plt.ylabel('Salary')
plt.title('Scatter Plot')
plt.show()
```
- Pair Plot: `sns.pairplot(data)`.
```python
sns.pairplot(data=df, hue='City')
plt.title('Pair Plot')
plt.show()
```
- Box Plot: `sns.boxplot(x, y, data)`.
```python
sns.boxplot(x='Gender', y='Salary', data=df)
plt.xlabel('Gender')
plt.ylabel('Salary')
plt.title('Box Plot')
plt.show()
```
- Violin Plot: `sns.violinplot(x, y, data)`.
```python
sns.violinplot(x='Gender', y='Age', data=df)
plt.xlabel('Gender')
plt.ylabel('Age')
plt.title('Violin Plot')
plt.show()
```
- Heatmap: `sns.heatmap(data)`.
```python
correlation_matrix = df.corr()
sns.heatmap(data=correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
```

## Data Analysis with Pandas

- `df.groupby('column').agg(func)`: Group and aggregate.
```python
grouped = df.groupby('City').agg({'Age': 'mean', 'Salary': 'sum'})
```
- `df.pivot_table(values, index, columns, aggfunc)`: Create pivot table.
```python
pivot_table = df.pivot_table(values='Salary', index='Gender', columns='City', aggfunc='mean')
```
- `pd.crosstab(index, columns)`: Create cross-tabulation.
```python
cross_tab = pd.crosstab(index=df['Gender'], columns=df['City'])
```
- `df.merge(other_df, on='key_column', how)`: Merge DataFrames.
```python
merged_df = df.merge(other_df, on='ID', how='inner')
```
- `df.join(other_df, on='key_column', how)`: Join DataFrames.
```python
joined_df = df.join(other_df.set_index('ID'), on='ID', how='inner')
```
- `df.apply(func, axis)`: Apply function to rows/columns.
```python
def custom_function(row):
    return row['Age'] * row['Salary']

df['Custom_Column'] = df.apply(custom_function, axis=1)
```

## Handling and Processing Data Files

### CSV

- `pd.read_csv(file_path)`: Read CSV file.
```python
import pandas as pd

df = pd.read_csv('data.csv')
```
- `df.to_csv(file_path, index)`: Save DataFrame to CSV.
```python
df.to_csv('new_data.csv', index=False)
```

### Excel

- `pd.read_excel(file_path, sheet_name)`: Read Excel file.
```python
import pandas as pd

df = pd.read_excel('data.xlsx', sheet_name='Sheet1')
```
- `df.to_excel(file_path, sheet_name, index)`: Save DataFrame to Excel.
```python
df.to_excel('new_data.xlsx', sheet_name='Sheet1', index=False)
```

### JSON

- `pd.read_json(file_path)`: Read JSON file.
```python


import pandas as pd

df = pd.read_json('data.json')
```
- `df.to_json(file_path)`: Save DataFrame to JSON.
```python
df.to_json('new_data.json', orient='records')
```

### SQL

- `pd.read_sql(query, connection)`: Read SQL query result.
```python
import pandas as pd
import sqlite3

connection = sqlite3.connect('database.db')
query = 'SELECT * FROM customers'
df = pd.read_sql(query, connection)
```
- `df.to_sql(table_name, connection)`: Save DataFrame to SQL.
```python
df.to_sql('new_customers', connection, if_exists='replace', index=False)
```

## Basic Machine Learning with Scikit-Learn

### Importing Scikit-Learn

- `from sklearn import [module]`: Import module.
```python
from sklearn import datasets
```
- `from sklearn.model_selection import train_test_split`: Train-test split.
```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
- `from sklearn.metrics import [metric]`: Import evaluation metrics.
```python
from sklearn.metrics import accuracy_score

## Preprocessing

- `from sklearn.preprocessing import [preprocessor]`: Import preprocessor.
```python
from sklearn.preprocessing import StandardScaler
```
- `preprocessor.fit(X)`: Fit preprocessor to data.
```python
scaler = StandardScaler()
scaler.fit(X_train)
```
- `X_transformed = preprocessor.transform(X)`: Transform data.
```python
X_train_scaled = scaler.transform(X_train)
X_test_scaled = scaler.transform(X_test)

### Models

- `from sklearn.[model] import [estimator]`: Import estimator.
```python
from sklearn.linear_model import LogisticRegression
```
- `estimator = [EstimatorClass]()`: Create an instance.
```python
model = LogisticRegression()
```
- `estimator.fit(X_train, y_train)`: Train the model.
```python
model.fit(X_train, y_train)
```
- `y_pred = estimator.predict(X_test)`: Predict using the model.
```python
y_pred = model.predict(X_test)

### Evaluation

- `from sklearn.metrics import [metric]`: Import metric.
```python
from sklearn.metrics import accuracy_score
```
- `score = metric(y_true, y_pred)`: Calculate metric score
```python
accuracy = accuracy_score(y_test, y_pred)
```

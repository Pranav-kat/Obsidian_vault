---
share: true
---

# Comprehensive Data Science Libraries Cheatsheet

## Pandas for Data Manipulation

### Data Structures

- `pd.Series(data, index)`: Create a Series.
- `pd.DataFrame(data, index, columns)`: Create a DataFrame.

### Data Loading and Inspection

- `df.head()`, `df.tail()`: View first/last rows.
- `df.info()`: Summary of DataFrame.
- `df.describe()`: Descriptive statistics.
- `df.shape`: Number of rows and columns.
- `df.columns`, `df.index`: Access columns and index.
- `df.dtypes`: Data types of columns.

### Data Selection and Manipulation

- `df['column']`, `df[['col1', 'col2']]`: Access columns.
- `df.loc[row_indexer, col_indexer]`: Label-based indexing.
- `df.iloc[row_indexer, col_indexer]`: Integer-based indexing.
- `df.query('condition')`: Filter rows using query.
- `df.drop(columns=['col1'])`: Drop columns.
- `df.drop(index=[row_index])`: Drop rows.
- `df.rename(columns={'old_name': 'new_name'})`: Rename columns.
- `df.sort_values(by='column')`: Sort rows.
- `df.groupby('column').agg(func)`: Group and aggregate.

### Data Cleaning

- `df.drop_duplicates()`: Remove duplicates.
- `df.fillna(value)`: Fill missing values.
- `df.dropna()`: Remove rows with missing values.

## NumPy for Numerical Operations

### Basics

- `import numpy as np`: Import NumPy.
- `np.array([data])`: Create a NumPy array.
- `array.shape`: Shape of the array.
- `array.ndim`: Number of dimensions.
- `array.dtype`: Data type of elements.

### Array Manipulation

- `np.reshape(array, new_shape)`: Reshape array.
- `np.concatenate(arrays, axis)`: Concatenate arrays.
- `np.split(array, indices_or_sections)`: Split array.
- `np.vstack(array1, array2)`: Vertically stack arrays.
- `np.hstack(array1, array2)`: Horizontally stack arrays.

### Numerical Operations

- `np.mean(array)`, `np.median(array)`: Mean, median.
- `np.min(array)`, `np.max(array)`: Minimum, maximum.
- `np.std(array)`, `np.var(array)`: Standard deviation, variance.
- `np.sum(array)`: Sum of array elements.

## Matplotlib and Seaborn for Data Visualization

### Matplotlib

- `import matplotlib.pyplot as plt`: Import Matplotlib.
- Line Plot: `plt.plot(x, y)`.
- Scatter Plot: `plt.scatter(x, y)`.
- Bar Plot: `plt.bar(x, y)`.
- Histogram: `plt.hist(data, bins)`.
- Pie Chart: `plt.pie(data, labels)`.
- Customize: `plt.title()`, `plt.xlabel()`, `plt.ylabel()`.

### Seaborn

- `import seaborn as sns`: Import Seaborn.
- Scatter Plot: `sns.scatterplot(x, y, data)`.
- Pair Plot: `sns.pairplot(data)`.
- Box Plot: `sns.boxplot(x, y, data)`.
- Violin Plot: `sns.violinplot(x, y, data)`.
- Heatmap: `sns.heatmap(data)`.
- Customize: `sns.set(style)`, `sns.set_palette()`.

## Data Analysis with Pandas

- `df.groupby('column').agg(func)`: Group and aggregate.
- `df.pivot_table(values, index, columns, aggfunc)`: Create pivot table.
- `pd.crosstab(index, columns)`: Create cross-tabulation.
- `df.merge(other_df, on='key_column', how)`: Merge DataFrames.
- `df.join(other_df, on='key_column', how)`: Join DataFrames.
- `df.apply(func, axis)`: Apply function to rows/columns.

## Handling and Processing Data Files

### CSV

- `pd.read_csv(file_path)`: Read CSV file.
- `df.to_csv(file_path, index)`: Save DataFrame to CSV.

### Excel

- `pd.read_excel(file_path, sheet_name)`: Read Excel file.
- `df.to_excel(file_path, sheet_name, index)`: Save DataFrame to Excel.

### JSON

- `pd.read_json(file_path)`: Read JSON file.
- `df.to_json(file_path)`: Save DataFrame to JSON.

### SQL

- `pd.read_sql(query, connection)`: Read SQL query result.
- `df.to_sql(table_name, connection)`: Save DataFrame to SQL.

## Basic Machine Learning with Scikit-Learn

### Importing Scikit-Learn

- `from sklearn import [module]`: Import module.
- `from sklearn.model_selection import train_test_split`: Train-test split.
- `from sklearn.metrics import [metric]`: Import evaluation metrics.

### Preprocessing

- `from sklearn.preprocessing import [preprocessor]`: Import preprocessor.
- `preprocessor.fit(X)`: Fit preprocessor to data.
- `X_transformed = preprocessor.transform(X)`: Transform data.

### Models

- `from sklearn.[model] import [estimator]`: Import estimator.
- `estimator = [EstimatorClass]()`: Create an instance.
- `estimator.fit(X_train, y_train)`: Train the model.
- `y_pred = estimator.predict(X_test)`: Predict using the model.

### Evaluation

- `from sklearn.metrics import [metric]`: Import metric.
- `score = metric(y_true, y_pred)`: Calculate metric score.


# Important Pandas Syntax

## 1. Importing Pandas

```python
import pandas as pd
```

## 2. Creating DataFrames

```python
# From a dictionary
df = pd.DataFrame({
    'Column1': [1, 2, 3],
    'Column2': ['A', 'B', 'C']
})

# From a CSV file
df = pd.read_csv('filename.csv')

# From an Excel file
df = pd.read_excel('filename.xlsx')

# From a JSON file
df = pd.read_json('filename.json')
```

## 3. Viewing Data

```python
# Display the first few rows
df.head()

# Display the last few rows
df.tail()

# Display DataFrame info (e.g., data types and non-null counts)
df.info()

# Display basic statistics
df.describe()
```

## 4. Selecting Data

```python
# Select a single column
df['Column1']

# Select multiple columns
df[['Column1', 'Column2']]

# Select rows by index position
df.iloc[0]  # First row
df.iloc[0:5]  # First 5 rows

# Select rows by index label
df.loc[0]  # Row with index label 0
df.loc[0:5]  # Rows from index 0 to 5

# Conditional selection
df[df['Column1'] > 1]
```

## 5. Filtering and Sorting

```python
# Filter rows
df_filtered = df[df['Column1'] > 1]

# Sort by a column
df_sorted = df.sort_values(by='Column1', ascending=False)
```

## 6. Handling Missing Data

```python
# Check for missing values
df.isnull().sum()

# Drop rows with missing values
df_dropped = df.dropna()

# Fill missing values
df_filled = df.fillna(value='Default Value')
```

## 7. Grouping Data

```python
# Group by a column and calculate mean
df_grouped = df.groupby('Column1').mean()
```

## 8. Merging and Joining

```python
# Merge two DataFrames on a key column
df_merged = pd.merge(df1, df2, on='KeyColumn')

# Concatenate two DataFrames
df_concat = pd.concat([df1, df2])
```

## 9. Applying Functions

```python
# Apply a function to a column
df['NewColumn'] = df['Column1'].apply(lambda x: x * 2)

# Apply a function across rows or columns
df.apply(lambda row: row['Column1'] + row['Column2'], axis=1)
```

## 10. Saving Data

```python
# Save to CSV
df.to_csv('filename.csv', index=False)

# Save to Excel
df.to_excel('filename.xlsx', index=False)

# Save to JSON
df.to_json('filename.json')
```

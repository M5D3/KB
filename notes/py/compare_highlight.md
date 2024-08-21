# How to compare two dataframes

# How to compare two rows

## Setup

We'll use the following Dataframe:

```python
data = [('A',1, 0, 3, 1),
        ('A',1, 2, 5, 1),
        ('B',2, 1, 4, 3),
        ('B',3, 1, 0, 3),
        ('C',4, 3, 1, 2)]
cols = ('col_1', 'col_2', 'col_3', 'col_4', 'col_5' )
df = pd.DataFrame(data,
                 columns = cols)
```

| idx | col_1 | col_2 | col_3 | col_4 | col_5 |
| --- | ----- | ----- | ----- | ----- | ----- |
| 0   | A     | 1     | 0     | 3     | 1     |
| 1   | A     | 1     | 2     | 5     | 1     |
| 2   | B     | 2     | 1     | 4     | 3     |
| 3   | B     | 3     | 1     | 0     | 3     |
| 4   | C     | 4     | 3     | 1     | 2     |

## Compare two rows with highlighting

```python
# Function to compare rows with even group size and highlight the differences.

def highlight_rows(d):
    df = pd.DataFrame(columns=d.columns, index=d.index)

    for i in range(0,len(d.index),2):
        if d.loc[i,"grp_size"] % 2 == 0:
            df.iloc[[i, i+1]] = 'background: None'
            df.iloc[[i, i+1],d.iloc[i].fillna(0).ne(d.iloc[i+1].fillna(0))] = 'background-color: yellow'

    return df

# How to apply the style
df.style.apply(highlight_rows, axis=None)
```

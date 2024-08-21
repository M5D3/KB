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

|idx|col_1|	col_2|	col_3|	col_4|	col_5|
|---|---|---|---|---|---|
|0|A|1|0|3|1|
|1|A|1|2|5|1|
|2|B|2|1|4|3|
|3|B|3|1|0|3|
|4|C|4|3|1|2|

## Compare two rows with highlighting

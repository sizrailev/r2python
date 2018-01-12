# r2python
Making transitioning from R to Python easier. 

## Apply a function to a list and get a list of results back

### R
```r
# This is really a vector, but is treated as a list
vec <- c(1, 2, 3, 4, 5)
result <- lapply(vec, function(x) { x^2 })
```
To convert the result back to vector, one could use `sapply` or simply `unlist` the result.
```r
result <- unlist(lapply(vec, function(x) { x^2 }))

> result
[1]  1  4  9 16 25
```

### Python
```python
vec = [1, 2, 3, 4, 5]
def square(x):
    return x * x
result = map(square, vec)

>>> result
[1, 4, 9, 16, 25]
```

## Read a csv file

### R
```r
df <- read.csv("myfile.csv", stringsAsFactors = FALSE, sep = ",")
```

### Python
```python
import pandas as pd
df = pd.read_csv('myfile.csv', sep=',')
```

## Get dataframe's column names.

### R
```r
names(df)
```

### Python
```python
list(df)
```

## Work with a dataframe's column

### R
In R, a column `mycol` in a dataframe `df` can be addressed as `df$mycol` or `df[["mycol"]]`. The latter takes advantage of the fact that an R dataframe is a `list` of named columns of different type. A `list` also behaves as a dictionary, when elements are named, as it is in the case of a dataframe. The double square brackets address the list element using the key `"mycol"`. 

### Python
\[Is there a better way?\]
```python
col = df['mycol'].tolist()
```

## Print the first few rows of a dataframe

In R, use `head(df)`. In Python, use `df.head()`.

## Add a column to a dataframe

### R
```r
df$newcol <- vec
```

### Python
```python
df = df.assign(newcol=pd.Series(vec).values)
```

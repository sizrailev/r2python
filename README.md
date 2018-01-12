# r2python
Making transitioning from R to Python easier. 

## Apply a function to a list and get a list of results back

### R
```r
# This is really a vector, but is treated as a list
lst <- c(1, 2, 3, 4, 5)
result <- lapply(lst, function(x) { x^2 })
```
To convert the result back to vector, one could use `sapply` or simply `unlist` the result.
```r
result <- unlist(lapply(lst, function(x) { x^2 }))

> result
[1]  1  4  9 16 25
```

### Python
```python
lst = [1, 2, 3, 4, 5]
def square(x):
    return x * x
result = map(square, lst)

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

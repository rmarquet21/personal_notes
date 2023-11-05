---
tags:
  - library
  - pandas
---
```python
# Count the number of stores of each type 
store_counts = store_types["type"].value_counts() 
print(store_counts) 
```
```
A 11 
B 1 
Name: type, dtype: int64 
```

```python
# Get the proportion of stores of each type 
store_props = store_types["type"].value_counts(normalize=True) print(store_props) 
```
```
A 0.917 
B 0.083 
Name: type, dtype: float64
```

```python
# Count the number of each department number and sort 
dept_counts_sorted = store_depts['department'].value_counts(ascending=False)
print(dept_counts_sorted) 
```
```
1 12 
3 12 
5 12 
6 12 
7 12 
.. 
37 10 
48 8 
50 6 
39 4 
43 2 
Name: department, Length: 80, dtype: int64 
```

```python
# Get the proportion of departments of each number and sort 
dept_props_sorted = store_depts['department'].value_counts(normalize=True, ascending=False) 
print(dept_props_sorted)
```
```
1 0.013 
3 0.013 
5 0.013 
6 0.013 
7 0.013 
... 
37 0.011 
48 0.009 
50 0.006 
39 0.004 
43 0.002 
Name: department, Length: 80, dtype: float64
```
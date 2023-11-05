---
tags:
  - pandas
  - library
---
- To select only `"col_a"` of the DataFrame `df`, use `df["col_a"]`
```python
# Select the individuals column
individuals = homelessness["individuals"]

# Print the head of the result
print(individuals.head())
```
```
0 2570.0 
1 1434.0 
2 7259.0 
3 2280.0 
4 109008.0 
Name: individuals, dtype: float64
```

- To select `"col_a"` and `"col_b"` of `df`, use `df[["col_a", "col_b"]]`
```python
# Select the state and family_members columns 
state_fam = homelessness[["state", "family_members"]] 

# Print the head of the result 
print(state_fam.head())
```
```
  state      family_members 
0 Alabama    864.0 
1 Alaska     582.0 
2 Arizona    2606.0 
3 Arkansas   432.0 
4 California 20964.0
```
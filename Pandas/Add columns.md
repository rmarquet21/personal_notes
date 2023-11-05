---
tags:
  - library
  - pandas
---
```python
# Add total col as sum of individuals and family_members 
homelessness["total"] = homelessness["individuals"] + homelessness["family_members"] 
# Add p_individuals col as proportion of total that are individuals
homelessness["p_individuals"] = homelessness["individuals"] / homelessness["total"] 
# See the result 
print(homelessness)
```
```
  state    individuals family_members total  p_individuals 
0 Alabama  2570.0      864.0          3434.0 0.748 
1 Alaska   1434.0      582.0          2016.0 0.711 
2 Arizona  7259.0      2606.0         9865.0 0.736 
3 Arkansas 2280.0      432.0          2712.0 0.841
```
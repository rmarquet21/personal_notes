---
tags:
  - library
  - pandas
---
|Sort on …|Syntax|
|---|---|
|one column|`df.sort_values("breed")`|
|multiple columns|`df.sort_values(["breed", "weight_kg"])`|
|sort|`df.sort_values("breed", ascending=False)`|
|multiple sort|`df.sort_values(["breed", "weight_kg"], ascending=[True, False])`|
```python
# Sort homelessness by descending family members

homelessness_fam = homelessness.sort_values("family_members")
```


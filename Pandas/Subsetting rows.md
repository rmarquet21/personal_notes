---
tags:
  - library
  - pandas
---
```python
# Filter for rows where individuals is greater than 10000 
ind_gt_10k = homelessness[homelessness["individuals"] > 10000] 
# See the result 
print(ind_gt_10k)
```
```
   region             state            individuals family_members state_pop 
4  Pacific            California       109008.0    20964.0        39461588 
9  South              Atlantic Florida 21443.0     9587.0         21244317 
32 Mid-Atlantic       New York         39827.0     52070.0        19530351 
37 Pacific            Oregon           11139.0     3337.0         4181886 
43 West South Central Texas            19199.0     6111.0         28628666 
47 Pacific            Washington       16424.0     5880.0         7523869
```

```python
# Filter for rows where region is Mountain 
mountain_reg = homelessness[homelessness["region"] == "Mountain"] 
# See the result 
print(mountain_reg)
```
```
   region   state      individuals family_members state_pop 
2  Mountain Arizona    7259.0      2606.0         7158024 
5  Mountain Colorado   7607.0      3250.0         5691287 
12 Mountain Idaho      1297.0      715.0          1750536 
26 Mountain Montana    983.0       422.0          1060665 
28 Mountain Nevada     7058.0      486.0          3027341 
31 Mountain New Mexico 1949.0      602.0          2092741 
44 Mountain Utah       1904.0      972.0          3153550 
50 Mountain Wyoming    434.0       205.0          577601
```

```python
# Filter for rows where family_members is less than 1000 # and region is Pacific 
fam_lt_1k_pac = homelessness[(homelessness["family_members"] < 1000) & (homelessness["region"] == "Pacific")] 
# See the result 
print(fam_lt_1k_pac)
```
```
  region  state  individuals family_members state_pop 
1 Pacific Alaska 1434.0      582.0          735139
```

```python
# Subset for rows in South Atlantic or Mid-Atlantic regions 
condition = homelessness["region"].isin(["South Atlantic", "Mid-Atlantic"])
south_mid_atlantic = homelessness[condition] 
# See the result 
print(south_mid_atlantic)
```
```
   region         state                individuals family_members state_pop 
7  South Atlantic Delaware             708.0       374.0          965479 
8  South Atlantic District of Columbia 3770.0      3134.0         701547 
9  South Atlantic Florida              21443.0     9587.0         21244317 
10 South Atlantic Georgia              6943.0      2556.0         10511131 
20 South Atlantic Maryland             4914.0      2230.0         6035802 
30 Mid-Atlantic   New Jersey           6048.0      3350.0         8886025 
32 Mid-Atlantic   New York             39827.0     52070.0        19530351 
33 South Atlantic North Carolina       6451.0      2817.0         10381615 
38 Mid-Atlantic   Pennsylvania         8163.0      5349.0         12800922 
40 South Atlantic South Carolina       3082.0      851.0          5084156 
46 South Atlantic Virginia             3928.0      2047.0         8501286 
48 South Atlantic West Virginia        1021.0      222.0          1804291
```
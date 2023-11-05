---
tags:
  - pandas
  - library
---
```python
# Group by type; calc total weekly sales
sales_by_type = sales.groupby("type")["weekly_sales"].sum() 

# Group by type and is_holiday; calc total weekly sales 
sales_by_type_is_holiday = sales.groupby(["type", "is_holiday"])["weekly_sales"].sum() 
print(sales_by_type_is_holiday)
```
```
type  is_holiday 
A     False 2.337e+08 
      True 2.360e+04 
B     False 2.318e+07 
      True 1.621e+03 
Name: weekly_sales, dtype: float64
```

```python
# Import numpy with the alias np 
import numpy as np 

# For each store type, aggregate weekly_sales: get min, max, mean, and median 
sales_stats = sales.groupby("type")["weekly_sales"].agg([np.min, np.max, np.mean, np.median]) 
# Print sales_stats 
print(sales_stats) 

# For each store type, aggregate unemployment and fuel_price_usd_per_l: get min, max, mean, and median 
unemp_fuel_stats = sales.groupby("type")[["unemployment", "fuel_price_usd_per_l"]].agg([np.min, np.max, np.mean, np.median]) 
# Print unemp_fuel_stats 
print(unemp_fuel_stats)
```
```
      amin    amax      mean      median 
type 
A     -1098.0 293966.05 23674.667 11943.92 
B     -798.0  232558.51 25696.678 13336.08 

	  unemployment                fuel_price_usd_per_l 
	  amin  amax  mean  median    amin  amax  mean  median 
type 
A     3.879 8.992 7.973 8.067     0.664 1.107 0.745 0.735 
B     7.170 9.765 9.279 9.199     0.760 1.108 0.806 0.803
```
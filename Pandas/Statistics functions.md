---
tags:
  - pandas
  - library
---
```python
# A custom IQR function 
def iqr(column): 
	return column.quantile(0.75) - column.quantile(0.25) 
	
# Print IQR of the temperature_c column 
print(sales["temperature_c"].agg(iqr))
```
```
16.583333333333336
```

```python
# A custom IQR function 
def iqr(column): 
	return column.quantile(0.75) - column.quantile(0.25) 
# Update to print IQR of temperature_c, fuel_price_usd_per_l, & unemployment 
print(sales[["temperature_c", "fuel_price_usd_per_l", "unemployment"]].agg(iqr))
```
```
temperature_c        16.583 
fuel_price_usd_per_l 0.073 
unemployment         0.565 
dtype: float64
```

```python
# Import NumPy and create custom IQR function 
import numpy as np 
def iqr(column): 
	return column.quantile(0.75) - column.quantile(0.25) 
# Update to print IQR and median of temperature_c, fuel_price_usd_per_l, & unemployment 
print(sales[["temperature_c", "fuel_price_usd_per_l", "unemployment"]].agg([iqr, np.median]))
```
```
       temperature_c fuel_price_usd_per_l unemployment 
iqr    16.583        0.073                0.565 
median 16.967        0.743                8.099
```

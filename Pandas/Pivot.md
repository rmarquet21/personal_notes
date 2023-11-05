---
tags:
  - pandas
  - library
---
Le pivot permet à la fois de réaliser un `.groupby()` et d'ensuite exécuter un `.mean()`
```python
# Pivot for mean weekly_sales for each store type 
mean_sales_by_type = sales.pivot_table(values="weekly_sales", index="type") 

# Print mean_sales_by_type 
print(mean_sales_by_type)
```
```
      weekly_sales 
type 
A     23674.667 
B     25696.678
```

On peut aussi agréger plusieurs fonctions
```python
# Import NumPy as np 
import numpy as np 

# Pivot for mean and median weekly_sales for each store type 
mean_med_sales_by_type = sales.pivot_table(values="weekly_sales", index="type", aggfunc=[np.mean, np.median]) 

# Print mean_med_sales_by_type 
print(mean_med_sales_by_type)
```
```
      mean         median 
      weekly_sales weekly_sales 
type 
A     23674.667    11943.92 
B     25696.678    13336.08
```

Faire un pivot avec 2 variables est possible
```python
# Pivot for mean weekly_sales by store type and holiday 
mean_sales_by_type_holiday = sales.pivot_table(values="weekly_sales", index=["type"], columns="is_holiday") 

# Print mean_sales_by_type_holiday 
print(mean_sales_by_type_holiday)
```
```
is_holiday False     True 
type 
A          23768.584 590.045 
B          25751.981 810.705
```

Pour les valuers manquante `fill_value` permet de remplacer par la valeur que l'on souhaite
```python
# Print mean weekly_sales by department and type; fill missing values with 0
print(sales.pivot_table(values="weekly_sales", index="department", columns="type", fill_value=0))
```
```
type        A          B 
department 
1           30961.725  44050.627 
2           67600.159  112958.527 
3           17160.003  30580.655 
4           44285.399  51219.654 
5           34821.011  63236.875 
... ... ... 
95          123933.787 77082.102 
96          21367.043  9528.538 
97          28471.267  5828.873 
98          12875.423  217.428 
99          379.124    0.000 

[80 rows x 2 columns]
``` 

```python
# Print the mean weekly_sales by department and type; fill missing values with 0s; sum all rows and cols 
print(sales.pivot_table(values="weekly_sales", index="department", columns="type", fill_value=0, margins=True))
```
```
type A B All department 1 30961.725 44050.627 32052.467 2 67600.159 112958.527 71380.023 3 17160.003 30580.655 18278.391 4 44285.399 51219.654 44863.254 5 34821.011 63236.875 37189.000 ... ... ... ... 96 21367.043 9528.538 20337.608 97 28471.267 5828.873 26584.401 98 12875.423 217.428 11820.590 99 379.124 0.000 379.124 All 23674.667 25696.678 23843.950 [81 rows x 3 columns]
```

```python
# Add a year column to temperatures
temperatures["year"] = temperatures["date"].dt.year

# Pivot avg_temp_c by country and city vs year
temp_by_country_city_vs_year = temperatures.pivot_table("avg_temp_c", index=["country", "city"], columns="year")

# See the result
print(temp_by_country_city_vs_year)
```
```
year                              2000    2001    2002    2003    2004  ...    2009    2010    2011    2012    2013
country       city                                                      ...                                        
Afghanistan   Kabul             15.823  15.848  15.715  15.133  16.128  ...  15.093  15.676  15.812  14.510  16.206
Angola        Luanda            24.410  24.427  24.791  24.867  24.216  ...  24.325  24.440  24.151  24.240  24.554
Australia     Melbourne         14.320  14.180  14.076  13.986  13.742  ...  14.647  14.232  14.191  14.269  14.742
              Sydney            17.567  17.854  17.734  17.592  17.870  ...  18.176  17.999  17.713  17.474  18.090
Bangladesh    Dhaka             25.905  25.931  26.095  25.927  26.136  ...  26.536  26.648  25.803  26.284  26.587
...                                ...     ...     ...     ...     ...  ...     ...     ...     ...     ...     ...
United States Chicago           11.090  11.703  11.532  10.482  10.943  ...  10.298  11.816  11.214  12.821  11.587
              Los Angeles       16.643  16.466  16.430  16.945  16.553  ...  16.677  15.887  15.875  17.090  18.121
              New York           9.969  10.931  11.252   9.836  10.389  ...  10.142  11.358  11.272  11.971  12.164
Vietnam       Ho Chi Minh City  27.589  27.832  28.065  27.828  27.687  ...  27.853  28.282  27.675  28.249  28.455
Zimbabwe      Harare            20.284  20.861  21.079  20.889  20.308  ...  20.524  21.166  20.782  20.523  19.756

[100 rows x 14 columns]
---
tags:
  - pandas
  - library
---
```python
# Drop duplicate store/type combinations 
store_types = sales.drop_duplicates(["store", "type"]) 
print(store_types.head())

# Drop duplicate store/department combinations 
store_depts = sales.drop_duplicates(["store", "department"]) print(store_depts.head()) 

# Subset the rows where is_holiday is True and drop duplicate dates 
holiday_dates = sales[sales["is_holiday"]].drop_duplicates("date") 

# Print date col of holiday_dates 
print(holiday_dates["date"])
```
```
store type department date weekly_sales is_holiday temperature_c fuel_price_usd_per_l unemployment 
0 1 A 1 2010-02-05 24924.50 False 5.728 0.679 8.106 
901 2 A 1 2010-02-05 35034.06 False 4.550 0.679 8.324 
1798 4 A 1 2010-02-05 38724.42 False 6.533 0.686 8.623 
2699 6 A 1 2010-02-05 25619.00 False 4.683 0.679 7.259 
3593 10 B 1 2010-02-05 40212.84 False 12.411 0.782 9.765 

store type department date weekly_sales is_holiday temperature_c fuel_price_usd_per_l unemployment 
0 1 A 1 2010-02-05 24924.50 False 5.728 0.679 8.106 
12 1 A 2 2010-02-05 50605.27 False 5.728 0.679 8.106 
24 1 A 3 2010-02-05 13740.12 False 5.728 0.679 8.106 
36 1 A 4 2010-02-05 39954.04 False 5.728 0.679 8.106 
48 1 A 5 2010-02-05 32229.38 False 5.728 0.679 8.106 

498 2010-09-10 
691 2011-11-25 
2315 2010-02-12 
6735 2012-09-07 
6810 2010-12-31 
6815 2012-02-10 
6820 2011-09-09 
Name: date, dtype: datetime64[ns]
```

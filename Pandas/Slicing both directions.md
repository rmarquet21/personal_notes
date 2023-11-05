---
tags:
  - pandas
  - library
---
```python
# Subset rows from India, Hyderabad to Iraq, Baghdad
print(temperatures_srt.loc[("India", "Hyderabad"):("Irag", "Baghdad")])
```
```
                          date  avg_temp_c
country   city                            
India     Hyderabad 2000-01-01      23.779
          Hyderabad 2000-02-01      25.826
          Hyderabad 2000-03-01      28.821
          Hyderabad 2000-04-01      32.698
          Hyderabad 2000-05-01      32.438
...                      ...         ...
Iraq    Baghdad   2013-05-01      28.673
        Baghdad   2013-06-01      33.803
        Baghdad   2013-07-01      36.392
        Baghdad   2013-08-01      35.463
        Baghdad   2013-09-01         NaN

[2145 rows x 2 columns]
```

```python
# Subset columns from date to avg_temp_c
print(temperatures_srt.loc[:, "date":"avg_temp_c"])
```
```
                         date  avg_temp_c
country     city                         
Afghanistan Kabul  2000-01-01       3.326
            Kabul  2000-02-01       3.454
            Kabul  2000-03-01       9.612
            Kabul  2000-04-01      17.925
            Kabul  2000-05-01      24.658
...                       ...         ...
Zimbabwe    Harare 2013-05-01      18.298
            Harare 2013-06-01      17.020
            Harare 2013-07-01      16.299
            Harare 2013-08-01      19.232
            Harare 2013-09-01         NaN

[16500 rows x 2 columns]
```

```python
# Subset in both directions at once
print(temperatures_srt.loc[("India", "Hyderabad"):("Irag", "Baghdad"),"date":"avg_temp_c"])
```
```
                          date  avg_temp_c
country   city                            
India     Hyderabad 2000-01-01      23.779
          Hyderabad 2000-02-01      25.826
          Hyderabad 2000-03-01      28.821
          Hyderabad 2000-04-01      32.698
          Hyderabad 2000-05-01      32.438
...                      ...         ...
Iraq    Baghdad   2013-05-01      28.673
        Baghdad   2013-06-01      33.803
        Baghdad   2013-07-01      36.392
        Baghdad   2013-08-01      35.463
        Baghdad   2013-09-01         NaN

[2145 rows x 2 columns]
```
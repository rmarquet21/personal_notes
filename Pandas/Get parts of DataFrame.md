---
tags:
  - library
  - pandas
---
- `.values`: Un tableau de valeurs NumPy bidimensionnel.
```python
# Print the values of homelessness
print(homelessness.values)
```
```
[['East South Central' 'Alabama' 2570.0 864.0 4887681] ['Pacific' 'Alaska' 1434.0 582.0 735139] ['Mountain' 'Arizona' 7259.0 2606.0 7158024] ['West South Central' 'Arkansas' 2280.0 432.0 3009733] ['Pacific' 'California' 109008.0 20964.0 39461588]]
```

- `.columns`: Un index de colonnes: les noms des colonnes.
```python
# Print the column index of homelessness
print(homelessness.columns)
```
```
Index(['region', 'state', 'individuals', 'family_members', 'state_pop'], dtype='object')
```

- `.index`: Un index pour les lignes : soit les numéros de ligne, soit les noms de ligne.
```python
# Print the row index of homelessness
print(homelessness.index)
```
```
Int64Index([0, 1, 2, 3, 4], dtype='int64')
```
---
tags:
  - library
  - numpy
---
Pour réaliser un tableau il existe 6 méthodes:
- À partir d'un d'une autre structure python (list, tuple, etc.)

```python
import numpy as np
np_height = np.array(height)
print(np_height)
```
```
array([1.73, 1.68, 1.71, 1.89, 1.79])
```

```python
np_weight = np.array(weight)
print(np_weight)
```
```
array([65.4, 59.2, 63.6, 88.4, 68.7])
```

```python
bmi = np_weight / np_height ** 2
print(bmi)
```
```
array([21.85171573, 20.97505669, 21.75028214, 24.7473475, 21.44127836])
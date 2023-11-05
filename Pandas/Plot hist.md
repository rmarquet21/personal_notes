---
tags:
  - chart
  - pandas
  - library
---
On affiche le prix moyens pour les avocats de type "conventional" et "organic" avec la valuer de [[Bins]] à 20.

```python
# Modify bins to 20
avocados[avocados["type"] == "conventional"]["avg_price"].hist(alpha=0.5, bins=20)

# Modify bins to 20
avocados[avocados["type"] == "organic"]["avg_price"].hist(alpha=0.5, bins=20)

# Add a legend
plt.legend(["conventional", "organic"])

# Show the plot
plt.show()
```
![[Pasted image 20231105165706.png]]
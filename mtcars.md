---
jupyter:
  jupytext:
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.6.0
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# MTCARS Example

The purpose of this notebook is to show the linkage between .ipynb and .md files via jupytext.


## Imports


```python
import pandas as pd
from sklearn.linear_model import LinearRegression
```

Read in the mtcars data set.  This was exported from R as a csv.  It's just not an example if the mtcars data set isn't used.

```python
mtcars = pd.read_csv("mtcars.csv")

# omit automatic transmissions
mtcars = mtcars[mtcars['am'] == 0]
mtcars
```

## Analysis
The first analysis is just a simple regression mode of the mpg by weight and hourse power of the cars.

```python
lm = LinearRegression().fit(mtcars[['wt', 'hp']], mtcars[['mpg']])
```

```python
print("Intercept: ", (lm.intercept_)[0])
print("weight: ", (lm.coef_)[0][0])
print("hp: ", (lm.coef_)[0][1])
```

<!-- #region variables={"round(abs((lm.coef_)[0][0]), 2)": "1.86"} -->
The average change in fuel economy for every 1000 lbs reduction in weight between to cars with equal horse power is {{round(abs((lm.coef_)[0][0]), 2)}} miles per gallon.
<!-- #endregion -->

# Krippendorff's Alpha
## Inter-rater reliability

This code has been taken from [bryant1410](https://github.com/pln-fing-udelar/fast-krippendorff )'s Fast implementation for alpha (thank you!). Minor modifications have been introduced to account for insufficient variation (Krippendorff (2004) Content Analysis, page 236) and numerical variations.

Insufficient variation refers to certain conditions in which observed and expected coincidences are identical (i.e., D_o = D_e = 0). In this case, alpha is indeterminate and Krippendorff assumes zero, since data cannot be reliable due to lack of variation. Additionally, triangular matrices were used to account for minor numerical variations.

### Usage
```python3
>>> import kripp_juan as k
>>> import numpy as np
>>> data = np.array([[1,1,1],[1,2,1],[1,3,2]])
>>> data
array([[1, 1, 1],
       [1, 2, 1],
       [1, 3, 2]])
>>> k.alpha(data, value_domain=[1,2,3], level_of_measurement='interval')
0.1578947368421053
```


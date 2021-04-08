# Recursive Feature Elimination
Sesuai dengan namanya, metode ini meng-eliminasi variabel secara rekursif menggunakan algoritma machine learning tertentu (misal Random Forest). Variabel akan dieliminasi satu per satu sampai ditemukan performa model seperti yang kita inginkan.

```
from sklearn.datasets import make_friedman1
from sklearn.feature_selection import RFE
from sklearn.svm import SVR

# dataset
X, y = make_friedman1(n_samples=50, n_features=10, random_state=0)

# Fitting
selector = RFE(SVR(kernel="linear"), n_features_to_select=5, step=1) # memilih 5 feature terbaik
selector = selector.fit(X, y)

# List of Features
selector.support_
selector.ranking_
```

## Flowchart
![](RFE.png)


## Refference
- https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.RFE.html
- https://www.researchgate.net/figure/A-flowchart-explaining-the-steps-involved-in-the-RFE-algorithm-in-detail_fig3_348934346
- https://www.youtube.com/watch?v=jXSw6em5whI
- https://machinelearningmastery.com/rfe-feature-selection-in-python/
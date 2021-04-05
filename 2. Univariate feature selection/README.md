# Univariate Feature Selection
Metode ini bekerja dengan cara memilih variabel atau feature berdasarkan uji statistik seperti regresi dan chi-squared.

## Algorithm
- f_classif
ANOVA F-value between label/feature for classification tasks.

- mutual_info_classif
Mutual information for a discrete target.

- chi2
Chi-squared stats of non-negative features for classification tasks.

- f_regression
F-value between label/feature for regression tasks.

- mutual_info_regression
Mutual information for a continuous target.

## Techniques

- SelectPercentile
Select features based on percentile of the highest scores.

- SelectKBest
Select features based on the k highest scores.

- SelectFpr
Select features based on a false positive rate test.

- SelectFdr
Select features based on an estimated false discovery rate.

- SelectFwe
Select features based on family-wise error rate.


## Usage

1. SelectKBest 
Feature yang terpilih berdasarkan ```K``` feature terbaik.
```
from sklearn.feature_selection import SelectKBest
from sklearn.feature_selection import chi2

X_new = SelectKBest(chi2, k=4).fit_transform(X, y)
X_new.shape
```


2. SelectPercentile 
removes all but a user-specified highest scoring percentage of features using common univariate statistical tests for each feature: false positive rate SelectFpr, false discovery rate SelectFdr, or family wise error SelectFwe.

```
from sklearn.feature_selection import chi2
from sklearn.feature_selection import SelectPercentile

X_new = SelectPercentile(chi2, percentile=10).fit_transform(X, y)
X_new.shape
```

3. GenericUnivariateSelect 
Metode ini merupakan generalisasi dari univariate feature selection, sehingga kita bisa meng-custom teknik yang akan digunakan. Teknik yan bisa dipilih adalah
```
    _selection_modes = {'percentile': SelectPercentile,
                        'k_best': SelectKBest,
                        'fpr': SelectFpr,
                        'fdr': SelectFdr,
                        'fwe': SelectFwe}
```

```
from sklearn.feature_selection import GenericUnivariateSelect
from sklearn.feature_selection import chi2

model = GenericUnivariateSelect(chi2, mode='k_best', param=4)
X_new = model.fit_transform(X, y)
```

## Refference
1. https://scikit-learn.org/stable/modules/feature_selection.html
2. https://github.com/scikit-learn/scikit-learn/blob/ef5cb84a/sklearn/feature_selection/univariate_selection.py#L368
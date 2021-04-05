# Feature Selection Using SelectFromModel
Metode ini menggunakan parameter (koef_,feature_importances_) untuk mengeluarkan variabel. Model yang digunakan bisa dari regresi logistik, random forest, dan decision tree.

```
from sklearn.ensemble import RandomForestClassifier

selector_logistic = SelectFromModel(estimator=LogisticRegression()).fit(X, y)
df_selector = pd.DataFrame(selector_logistic.transform(X))
```

## Refference
- https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.SelectFromModel.html


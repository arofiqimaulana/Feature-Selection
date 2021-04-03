# Removing features with low variance (Variance Treshold)

Ide dibalik metode ini adalah mengeluarkan variabel yang variance nya lebih dari nilai tertentu (treshold tertentu). Metode ini hanya menggunakan variabel X (tidak variabel Y).0

```
from sklearn.feature_selection import VarianceThreshold

treshold = VarianceThreshold(threshold=0.5) # menghapus variabel yang variance >- 0.5
X_train_varTreshold = treshold.fit_transform(X)

```
 
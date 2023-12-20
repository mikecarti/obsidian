```python

class MTE:
    def fit_transform(self, X: pd.DataFrame, y: np.array):
        """
        X: dataframe of only categorical variables
        y: real target variable
        """
        transformed_X = X.copy()
        mean_targets_on_train = {}

        for cat_col in X.columns:
            series = X[cat_col]
            transformed_series = np.empty(shape=series.shape)
            mean_targets_on_train[cat_col] = dict()
            for category in series.unique():
                mean_target = np.sum(y[series == category]) / len(series[series == category])
                transformed_series[series == category] = mean_target
                mean_targets_on_train[cat_col][category] = mean_target

            transformed_X[cat_col] = transformed_series

        self.mean_targets_on_train = mean_targets_on_train
        return transformed_X

    def transform(self, X:pd.DataFrame):
        """
        X: dataframe of only categorical variables
        y: real target variable
        """
        transformed_X = X.copy()
        for cat_col in X.columns:
            series = X[cat_col]
            transformed_series = np.empty(shape=series.shape)
            for category in series.unique():
                transformed_series[series == category] = self.mean_targets_on_train[cat_col][category]
            transformed_X[cat_col] = transformed_series

        return transformed_X

mte_enc = MTE()
X_train_mte = mte_enc.fit_transform(X_train, y_train)
X_test_mte = mte_enc.transform(X_test) 
```



### Related
[[Mean Target Encoding (MTE)]]
[[Smooth Mean Target Encoding (SMTE)]]
```python
from sklearn.compose import ColumnTransformer
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import OneHotEncoder, StandardScaler
from sklearn.linear_model import Ridge

assert list(X_train.columns) == list(X_test.columns)

categorical_features = ["store_and_fwd_flag", "weekday", "hour", "month", "anomaly_date"]
numerical_features = X_train.drop(columns=categorical_features).columns

preprocessor = ColumnTransformer(
    transformers=[
        ("num", StandardScaler(), numerical_features),
        ("cat", OneHotEncoder(), categorical_features)
    ]
)

model = Pipeline(
    steps=[
        ('preprocessor', preprocessor),
        ('regressor', Ridge())
    ]
)

model.fit(X_train, y_train)
```

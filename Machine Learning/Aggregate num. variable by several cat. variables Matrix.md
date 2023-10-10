Matrix similar to df.corr()

```python
df = pd.DataFrame()

num_variable = ""
categorical_cols = ["a","b","c"]

df.groupby(categorical_cols).median()[num_variable].unstack()
```

![[Pasted image 20231008182622.png]]
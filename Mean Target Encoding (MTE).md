Idea: change categorical feature on mean categorical feature

$$
\begin{align}
&f_{j}(x) \text{ - j-th categorical feature} \\ \\
&\text{bin. classification:} \\
&g_{j}(x, X) = \frac{{\sum_{i=1}^{\ell}(f_{i}(x_{i})=f_{j}(x))[y_{i}=+1]}}{\sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{j}(x)]} \\ \\
&\text{multiclass classification:} \\
&g_{jk}(x,X) = \frac{{\sum_{i=1}^{\ell} (f_{j}(x_{i})= f_{i}(x)})[y_{i}=k]}{{\sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{j}(x)]}}
\end{align}
$$

## Problem:
Data leak. 

Feature becomes dependent of feature ($y_{i}$). We can not look into target variable while we are working with the test data.

## Solutions:
### Cross Validation
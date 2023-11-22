
 Каждый категориальный признак заменяется на среднее значение целевой переменной по всем объектам, имеющим одинаковое значение в этом признаке.

Idea: change categorical feature on mean value for this categorical feature on other numerical feature. Feature engineering for classification.

$$
\begin{align}
&f_{j}(x) \text{ - j-th categorical feature} \\ \\
&\text{bin. classification:} \\
&g_{j}(x, X) = \frac{{\sum_{i=1}^{\ell}[f_{i}(x_{i})=f_{j}(x)][y_{i}=+1]}}{\sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{j}(x)]} \\ \\
&\text{multiclass classification:} \\
&g_{jk}(x,X) = \frac{{\sum_{i=1}^{\ell} [f_{j}(x_{i})= f_{i}(x)}][y_{i}=k]}{{\sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{j}(x)]}}
\end{align}
$$

## Example:
![[Pasted image 20231010131950.png|450]]


## Problems:
### 1) Data leak. 
Feature becomes dependent of feature ($y_{i}$). We can not look into target variable while we are working with the test data.
### Solutions:
- Cross Validation
- Зашумление $g_{j}(x, X) + \epsilon$    $\epsilon \sim \mathcal{N}(0, \sigma^{2})$
- Сглаживание
- Coding by time ([[CatBoost]])
$$
	\begin{gather}
g_{j(x, X)} = \frac{{\sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{j}(x)][y_{i}=+1]}}{\sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{i}(x)]} + (1-\lambda(n_{j})) \cdot \frac{1}{\ell}\sum_{i=1}^{\ell}[y_{i}=+1] \\
n_{j} = \sum_{i=1}^{\ell}[f_{j}(x_{i})=c_{j}] \\
\lambda(n) = \frac{1}{1+e^{-\alpha n - \beta}}   \qquad \alpha, \beta \text{ - hyper-params}
\end{gather}

$$



	![[Pasted image 20231010132344.png|]]
### 2) New non-seen category.
### Solutions:
- Average along all X
- trash bucket (one category for rare values)



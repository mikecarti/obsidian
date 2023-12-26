That is [[R^2]] with a penalty on number of regressors. As regressors buff the [[R^2]], this tries to work sort of as a [[Regularization]].
$$
R^{2}_{adj} = \frac{RSS/(n-k)}{TSS/(n-1)}
$$

TSS only consists of y, and we take $\bar{y}$ as one degree of freedom. For RSS we take $k$ degrees of freedom (k = num. of estimators)


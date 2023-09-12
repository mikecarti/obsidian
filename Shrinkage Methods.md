
# Regularization
## Ridge Regression

For fighting with outliers.
**Ridge fights better with outliers than Lasso**.

Ridge regression shrinks the regression coefficients by imposing a penalty on their size. 

  

$\hat{\beta}^{ridge} = argmin_\beta \{\sum_{i=1}^N(y_i - \beta_0 - \sum_{j=1}^p x_{ij}\beta_j)^2 + \alpha \sum_{j=1}^p \beta_j^2\}$

  

Writing the criterion before in matrix form

  

$\mathrm{RSS}(\alpha) = (\boldsymbol{y} - \boldsymbol{X}\beta)^T (\boldsymbol{y} - \boldsymbol{X}\beta) + \alpha\beta^T\beta = \mathrm{RSS}(\beta) + \alpha\beta^T\beta$

  

The ridge regression solutions are

  

$$\hat{\beta}^{ridge} = (\boldsymbol{X}^T\boldsymbol{X} + \alpha\boldsymbol{I})^{-1}\boldsymbol{X}^T\boldsymbol{y}$$



## Lasso Regression

The Lasso is a shrinkage method like ridge. The main difference is that lasso penalty makes the solutions nonlinear in the $y_i$, and there is no closed form expression as in ridge regression.

  

$\hat{\beta}^{lasso} = argmin_\beta \{\frac{1}{2}\sum_{i=1}^N(y_i - \beta_0 - \sum_{j=1}^p x_{ij}\beta_j)^2 + \alpha \sum_{j=1}^p |\beta_j|)\}$

## Differentiation
[[Sub-Gradient]] is used. That is, using a super-position for gradient.[-1,1] in x=0.

## BIC Regression
...
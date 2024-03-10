$$
y = \beta_{0} + \beta_{1}x + u
$$

# Coefficients 
$$
\hat{\beta_{0}} = \bar{y} - \hat{\beta}_{1}\bar{x}
$$
$$
\hat{\beta_{1}} = \hat{\rho}_{xy} \cdot \left( \frac{\hat{\sigma}_{y}}{\hat{\sigma}_{x}} \right)= \frac{{\sum\limits_{i=1}^{n}(x_{i}- \bar{x})(y_{i}-\bar{y})}}{\sum\limits_{i=1}^{n}(x_{i}-\bar{x})^{2}}
$$
### Standard Errors

$$
sd (\hat{\beta}_{1}) = \frac{\sigma}{\sqrt{ TSS_{x} }} = \frac{\sigma}{\left( \sum\limits_{i=1}^{n}(x_{i}-\bar{x})^{2} \right)^{1/2}}
$$
Where [[Ordinary Least Squares (OLS)#Total sum of squares (TSS)|TSS]] is Total Sum of Squares in [[Ordinary Least Squares (OLS)]].


## Related
[[Regression Through the Origin]]
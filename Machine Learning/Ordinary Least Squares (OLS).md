$$
e_{i} = Y_{i} - (\hat{\beta}_{0}+\hat{\beta}_{1}x_{i})
$$
$$
\sum_{i=1}^{n}{e_{i}^2}\to \min\limits_{\beta_{0}, \beta_{1}}
$$
*Note*: Residuals are not errors. Errors are R.V. Residuals are just numbers. Do not confuse them. 

# Total sum of squares (TSS)
$$
TSS = RSS + ESS
$$
$$
TSS = \sum\limits_{i=1}^{n}(y_{i}- \bar{y}_{i})^{2}
$$
## Residual sum of squares (RSS)
$$
\text{RSS} = \sum_{i=1}^{n}e^2_{i}
$$
TSS is the measure of how spread out the $y_{i}$ in the sample. It is connected to [[Variance#Connection to Ordinary Least Squares (OLS) TSS|Sample Variance]]

## Error sum of squares (ESS)
$$
\text{ESS} = \sum_{i=1}^{n}(\hat{y}_{i}-\bar{y})
$$

# Properties
$y_{i} = \hat{y}_{i}+\hat{u}_{i}$
$\hat{u}_{i} = y_{i} - \hat{y}_{i}$
## Fitted Values and Residuals
if $\hat{u}_{i}$ > 0, model under-predicts
if $\hat{u}_{i} <0$  model over-predicts

## Assumptions of OLS 
### Conditional Mean
$$
E(u\mid x) = 0
$$

### [[Homoscedasticity]]
$$
Var(u\mid x) = \sigma^{2}
$$

## Properties of OLS Estimators
### Unbiasedness
$$
E(\hat{\beta}_{i}) = \beta_{i}
$$


# Related:
[[R^2]]
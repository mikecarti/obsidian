
$$
y_{i}=\alpha
$$
## 1) Multicolinearity $rank(X)=k+1$ for $k$ regressors
## 2) X - deterministic 
## 3) $E(e_{i}) = 0$ ⇾ unbiased
## 4) $Var(e_{i})=\sigma^2$ → const
## 5) $Cov(e_{i}, e_{j})=0$

# In other words: 
## 1)  [[Linearity]]: the parameters we are estimating using the OLS method must be themselves linear.
## 2) Random: our data must have been randomly sampled from the population.
## 3) Non-[[Collinearity]]: the regressors being calculated aren’t perfectly correlated with each other.
## 4) [[Exogenous & Endogenous Variables]]: the regressors aren’t correlated with the error term.
## 5) Homoscedasticity: no matter what the values of our regressors might be, the error of the variance is constant.

## The Gauss-Markov Assumptions In Algebra

![[BLUE - Best Linear Unbiased Estimator]]

##  Specification
Inefficiency - Variance of error
Biasness - Mean error

Omitted Variable Bias → biased → inconsistency
Excessiveness → Inefficiency
Non-Linearity → biased → inconsistency 

# Confidence interval for estimator
$$
\hat{\beta} \pm t_{n-k}  \cdot  se(\hat{\beta})
$$
$n$ - num of observations
$k$  - num of degrees of freedom (parameters to estimate)

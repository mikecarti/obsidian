# in [[Simple Linear Regression]]
$$
sd (\hat{\beta}_{1}) = \frac{\sigma}{\sqrt{ TSS_{x} }}
$$
Where [[Ordinary Least Squares (OLS)#Total sum of squares (TSS)|TSS]] is Total Sum of Squares in [[Ordinary Least Squares (OLS)]].


One way to view these restrictions is this: if we know $n - 2$ of the residuals, we can always get the 
other two residuals by using the restrictions implied by the first order conditions:
$$
\sum\limits_{i=1}^{n}\hat{u}_{i} = 0 \quad \sum\limits_{i=1}^{n}x_{i}\hat{u}_{i} = 0
$$
Thus, there are only $n-2$ degrees of freedom in the [[Ordinary Least Squares (OLS)|OLS]] residuals, as opposed to n degrees of freedom 
in the errors. 

The unbiased estimator of $\sigma^{2}$:
$$
\hat{\sigma}^{2} = \frac{1}{(n-2)}\sum\limits_{i=1}^{n}\hat{u}_{i}^{2} = \frac{RSS}{n-2}
$$
[[Ordinary Least Squares (OLS)#Residual sum of squares (RSS)|Where RSS is...]]

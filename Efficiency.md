$\sim$ How small is population (true) [[Variance]] of our estimator. This term should be used for comparison of *different* estimators, sample size should remain the same.


## Example: Population [[Variance]] of the generalized [[Estimators|estimator]] 
$$
\begin{align}
\sigma_{Z}^{2}  &= var(\lambda_{1}X_{1} + \lambda_{2}X_{2}) \\
&= var(\lambda_{1}X_{1}) + var(\lambda_{2}X_{2}) + Cov(\lambda_{1}X_{1},\lambda_{2}X_{2}) \\
&= \{ \text{Assuming that X1 and X2 are independent} \} \\
&= \lambda_{1}^{2}var(X_{1}) + \lambda_{2}^{2}var(X_{2})  \\
\end{align}
$$
By [[Unbiasedness]] $\lambda_{1}+\lambda_{2}=1$ if we want an unbiased estimator, therefore:
$$
\begin{align}
\sigma_{Z}^{2} &= (\lambda_{1}^{2} + \lambda_{2}^{2})\sigma_{X}^{2} \\
& = \sigma_{X}^{2}(2\lambda_{1}^{2} -2\lambda_{1} + 1) \to \min_{\lambda_{1}}  \\
&4\lambda - 2 = 0 \text{ first derivative} \implies \lambda = 0.5  \\
\implies \sigma_{Z}^{2} &= \frac{1}{2}\sigma^{2}_{X} \text{ for 2 observations (unbiased efficient sample mean)}
\end{align}
$$


The idea behind this method is to estimate such parameters for which observed data has the maximum joint probability (data is more probable to appear with such parameters of [[Joint Probability Distribution]].)

# Intuition
Select such parameters of distribution, that make observed data most probable. It is the probability that we would observe what we actually do observe in our data.

# Formally
$$
\begin{align}
&{\displaystyle \;\theta =\left[\theta _{1},\,\theta _{2},\,\ldots ,\,\theta _{k}\right]^{\mathsf {T}}\;} - \text{parameters}\\
&\mathbf{y} = \left( y_{1},y_{2}\dots,y_{n} \right) - \text{ observed data sample} \\
&{\displaystyle {\mathcal {L}}_{n}(\theta )={\mathcal {L}}_{n}(\theta ;\mathbf {y} )=f_{n}(\mathbf {y} ;\theta )\;,} - \text{Likelihood Function} \\ \\

&\text{For independent and i.i.d R.V,} \quad   \\
&f_{n}(y;\theta)  \text{ will be the product of density functions:} \\
&{\displaystyle f_{n}(\mathbf {y} ;\theta )=\prod _{k=1}^{n}\,f_{k}^{\mathsf {univar}}(y_{k};\theta )~.} \\
&{\displaystyle {\hat {\theta }}={\underset {\theta \in \Theta }{\operatorname {arg\;max} }}\,{\mathcal {L}}_{n}(\theta \,;\mathbf {y} )~.} \\ \\

&\mathcal{L} = \prod_{i=1}^{n} P(X=x_{i}) \to \max_{\theta} \\
&\ln \mathcal{L} = \sum_{i=1}^{n}\ln f(x_{i}) = \sum_{i=1}^{n}\ln \mathcal{L}(X=x_{i})
\end{align}
$$

## Properties of Maximum Likelihood Estimators
- [[Consistent Estimator]]
- [[Efficient Estimator|Asymptotically Efficient]]
- [[Asymptotical Normality]]
	$$
	\begin{align}
\hat{\theta_{ML}} \sim^{asy.} \mathcal{N}(\theta, I(\theta)^{-1}) \\
I(\theta ) = - E\left( \frac{\sigma^{2}\ln \mathcal{L}}{\sigma\theta^{2}} \right)
\end{align}
$$
- [[Invariant]]
	 $$
\begin{align}
\hat{\rho(\theta)}_{ML}
\end{align} = \rho(\hat{\theta}_{ML})
\hat{E(x^{2})}_{ML} = \hat{\sigma^{2}}_{ML} + \hat{\mu}^{2}_{ML}
$$
[[Delta Method]]


# Connection to [[Ordinary Least Squares (OLS)]]
$$
\hat{\beta}_{ML} = \hat{\beta}_{OLS} = (x^{T}x)^{-1}x^{T}y
$$
$$
\hat{\sigma}^{2}_{ML}=\frac{RSS}{n}
$$
[[Linear Regression with Box-Cox Transformation]] coefficients can not be estimated with [[Ordinary Least Squares (OLS)]], but can be estimated with [[Maximum Likelihood Estimation (MLE)]]

## Regularity Conditions
![[Pasted image 20240208135020.png]]'


# Testing hypotheses 
$H_{0}: \; g(\theta)= 0$
$H_{1}: \; g(\theta) \neq 0$

![[Likelihood Ratio (LR) Test]]


![[Wald Test]]



![[Lagrange Multiplier (LM) Test]] 
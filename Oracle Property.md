True model:
$$
y = \beta_{1}x_{1} + \dots \beta_{p_{0}}x_{p_{0}}+ \epsilon
$$
Set $x_{1}, \dots, x_{p}$    $p> p_{0}$; it includes  $x_{1}, \dots, x_{p_{0}}$
Then the estimator $\hat{\beta}$ possesses oracle property if:
1) $\hat{\beta}; j \, \cancel{ \in } \, 1, \dots, p_{0}$    $\hat{\beta}_{j} \to 0$
$\hat{\beta}_j; j \, \in \, 1,\dots,p_{0}$     $\hat{\beta_{j}} \cancel{ \to }0$
2) $\sqrt{ n }\left( \hat{\beta}_{j}-\beta_{j} \right)\to_{d} N(0, \Sigma)$
Where $d$ is a distribution, and this property is a property of [[Maximum Likelihood Estimation (MLE)]]

$\Sigma$ - is the [[Covariance Matrix]] of [[Estimators|estimator]] estimated using only the true subset $x_{1}, \dots, x_{p_{0}}$

## Estimators with that property
![[Lasso#Adoptive LASSO]]


![[SCAD (Smoothly Clipped Absolute Deviation)]]
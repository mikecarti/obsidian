### Popular estimators:
$$
\begin{align}
\hat{\theta}_{OLS} && \hat{\theta}_{MaxL} && \hat{\theta}_{MoM} 
\end{align}
$$

$\hat{\theta} - \text{Random Variable}$
$\theta - \text{Estimated Value (Real Number)}$

### Properties: 
1) [[Linearity]]
2) Unbiasedness     $E[\hat{\theta}] = \theta$
3) Consistency        $p\lim_{ n \to \infty }(|\hat{\theta}-\theta|<\epsilon) \;\;\ \hat{\theta} \to \theta$
4) Efficiency            $Var[\hat{\theta}] \leq Var[\tilde{\theta}]$,          $\hat{\theta}, \tilde{\theta} \in CL_{Lue}$   ($CL_{Lue}$ - Class of Linearly unbiased estimators)
5) Normality           $\hat{\theta}_{ML}$  ~ $N(\theta, Var(\hat{\theta})), n \to \infty$

###  $\lim_{ n \to \infty }$ where n - number of observations.

![[Pasted image 20230907154543.png | 300]]

$$
\exists i,j: \quad Cov(\epsilon_{i}, \epsilon_{j}) \neq 0
$$
For errors $\epsilon_{i}$ and $\epsilon_{j}$.

Violation of last assumption of [[Gauss Markov Theorem]]
$$
cov(\epsilon) = \Omega \neq \begin{bmatrix}
\ddots{} &  0  &  0  \\
0  & \ddots{}  &  0 \\
0  & 0 & \ddots{}
\end{bmatrix} 
$$
Consequences: (of [[Heteroskedasticity]])
$\hat{\beta}_{OLS}$ is not [[Efficient Estimator|efficient]] but [[Unbiasedness|unbiased]] and [[Consistent Estimator|consistent]].
$\hat{V}_{OLS}(\hat{\beta}_{OLS})$ is not [[Consistent Estimator|consistent]]. 

## Sources:
1) Time (can not be for a problem for [[Cross-Sectional Data]]. Only for [[Time Series Data]] data.)
2) Spatial auto-correlation         

## Solutions
### ![[Generalized least squares (GLS)]]
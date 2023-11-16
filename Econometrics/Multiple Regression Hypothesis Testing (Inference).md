**

## Estimator of variance of error
$\epsilon \sim N(0; \sigma^2)$
$y_{i}=x_{\beta}+\epsilon_{i}$
$\hat{\beta} = (x^Tx)^{-1}x^Ty$
$E(\hat{\beta})=\beta$
$V(\hat{\beta})=\sigma^2(x^Tx)^{-1}$

$$
\frac{{\beta}_{j}-{\sigma}}{\sqrt{ V(\hat{\beta_{j}}) }} \sim N(0;1)
$$
$M = (I-x(x^Tx)^{-1}x^T)$ - residual making matrix
$M \cdot Y=e$
$RSS = \sum e_{i}^2 = e^te =Y^T \cdot M^TM \cdot Y = Y^TMY =$
$= (x\beta+\epsilon)^TM(x_{\beta}+\epsilon) = \cancelto{0}{ \beta^Tx^TMx\beta+\epsilon^TMx\beta } + \cancelto{0}{ \beta^Tx^TM\epsilon  }+ \epsilon^TM\epsilon =$
$= \epsilon^TM\epsilon = E(\epsilon^TM\epsilon)= E(tr(M\epsilon\epsilon^T) - \sigma^2tr(M)) =$
$= \sigma^2  \cdot tr[I-x(x^Tx)^{-1}x^T] =$
$= \sigma^2(rank(I_{n}) - rank(x(x^Tx)^{-1}x^T))=\sigma^2(n-k-1)$
$\hat{\sigma}^2_{\epsilon}=\frac{RSS}{n-k-1}$ Is a pretty good estimator of variance of error.



Note:
$tr(\text{idempotent matrix}) = \text{ Rank(idempotent matrix)}$

$\epsilon \text{ - RV error}$
$e \text{ - just an error}$


$\hat{V}(\hat{\beta})=\hat{\sigma}^2_{\epsilon}(x^Tx)^{-1}$ according to [[Cochrane's Theorem]]
then 
$\frac{{\hat{\beta}-c}}{\sqrt{ \hat{V}\hat{\beta}_{j} }} \sim t_{n-k-1}$

We can use this result to...
1) Test hypothesis
2) Confidence intervals $\implies \hat{b}_{j}\pm t_{1-\frac{\alpha}{2}; n-k-1}\sqrt{ \hat{v}(\hat{\beta}_{i}) }$


## How to test system of weights = 0

$H_{0}: RB = q$
$H_{A}: RB \neq q$

$$
F = \frac{{(RSS_{R}-RSS_{UR})/q}}{RSS_{UR}/(n-k-1)} \sim F_{q; n-k-1}
$$
$RSS_{UR}$ - $RSS$ of original model (unrestricted)
$RSS_{R}$ - $RSS$ with all the restrictions applied
$q = rank(R)$
$$
R = \begin{pmatrix}
0 & 0 \\
0 & I
\end{pmatrix}
$$
## Related
[[Linear Regression]]
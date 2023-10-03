$\epsilon \sim N(0; \sigma^2)$
$y_{i}=x_{\beta}+\epsilon_{i}$
$\hat{\beta} = (x^Tx)^{-1}x^Ty$
$E(\hat{\beta})=\beta$
$V(\hat{\beta})=\sigma^2(x^Tx)^{-1}$

$$
{\beta}_{j}-\frac{\sigma}{\sqrt{ V(\hat{\beta_{j}}) }} \sim N(0;1)
$$
$M = (I-x(x^Tx)^{-1}x^T$
$M \cdot Y=e$
$RSS = \sum e_{i}^2 = e^te =Y^T \cdot M^TM \cdot Y = Y^TMY =$
$= (x\beta+\epsilon)^TM(x_{\beta}+\epsilon) = \cancel{ \beta^Tx^TMx\beta+\epsilon^TMx\beta } + \cancel{ \beta^Tx^TM\epsilon  }+ \epsilon^TM\epsilon =$
$= \epsilon^TM\epsilon = E(\epsilon^TM\epsilon)= E(tr(M\epsilon\epsilon^T) - \sigma^2tr(M)) =$
$= \sigma^2  \cdot tr[I-x(x^Tx)^{-1}x^T] =$
$= \sigma^2(rank(I_{n}) - rank(x(x^Tx)^{-1}x^T))=\sigma^2(n-k-1)$

Note:
$tr(\text{idempotent matrix}) = \text{ Rank(idempotent matrix)}$

$\epsilon \text{ - RV error}$
$e \text{ - just an error}$



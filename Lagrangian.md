## Definition
$$
L(x,h,\nu) = f_{0}(x)+\sum\lambda_{i}f_{i}(x) + \sum\nu h_{i}(x) 
$$
For a task
$$
\begin{cases}
f_{0}(x) \to \min_{} \\
f_{i}(x) \leq 0 \\
f_{j}(x) = 0
\end{cases}
$$
$\lambda, \nu$ - Lagrangian Multiples



## Dual Function
$inf_{x} \;L(x,h,\nu)=g(\lambda,\nu) \text{ - Dual Function}$ 
$g(\lambda, \nu)$ - always [[Concave & Convex]] (вогнутая) and is a lower bound: $g(h,\nu)\leq f_{0}(x)$

$x^{'}$ - accepted point, so 
$f_{i}(x')\leq 0$
$h_{i}(x')=0$
$h_{i}>0$

$$
\begin{align}
L(x',h,\nu) = f_{0}(x')+ \sum\lambda_{i}f_{i}(x') + \sum\nu_{i}h_{i}(x') \leq f_{0}(x') \\
infL(x_{0},h,\nu)\leq L(x',h,\nu)\leq f_{0}(x')
\end{align}
$$
$$
\begin{align}
inf_{x} \; L(x,\lambda,\nu) \leq inf_{x_{a}}\;L(x,\nu,\lambda) \leq f_{0}(x') \\
x^{*} \quad  g(h,\nu)\leq f_{0}(x^{*}) \quad \quad
\end{align}
$$

### Dual Task
$$
\begin{cases}
g(h,\nu)\to \max_{h,\nu} \\
h_{i}\geq 0
\end{cases}
$$
#### Weak Duality
$$
g(h_{*}, \nu_{*}) \leq f_{0}(x_{*})
$$

#### Strong Duality
$$
g(h_{*}, \nu_{*}) = f_{0}(x_{*})
$$


##### Task1 (Example)
$$
\begin{cases}
\lvert\lvert x \rvert\rvert ^{2}\to \min_{} \\
Ax=b
\end{cases} \to \begin{cases}
\lvert\lvert x \rvert\rvert ^{2}\to \min_{} \\
Ax-b=0
\end{cases}
$$
Find a Dual Task 
$$
\begin{align}
L(x,\nu)=\lvert\lvert a \rvert\rvert ^{2}+\nu^{T}(Ax-b) \\
g(\nu)=inf_{x}\;L(x,\nu) \\
\nabla_{x}L(x,\nu)=2x+\nu^{T}A \quad  x_{0} = -\frac{1}{2}A^{T}\nu \\
L\left( -\frac{1}{2}A^{T}\nu, \nu \right) = \frac{1}{4}A^{T}\nu \cdot \nu A^{T} = \\
= \frac{1}{4}\nu^{T} AA^{T}\nu + \nu^{T}\left( A\left( -\frac{1}{2}A^{T}\nu \right)-b \right)=  \\
= -\frac{1}{4}\nu^{T}AA^{T}\nu - \nu^{T}b = g(\nu)
\end{align}
$$
## Sleiter Condition
![[Slater's condition]]
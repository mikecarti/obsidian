
$$
M_{X(t)} = E(e^{tX}) =
\begin{cases}
\sum\limits_{x}e^{tX}f_{X}(x) & \text{if X discrete} \\
\int_{-\infty}^{\infty}e^{tX}  \, dx & \text{if X continuous}
\end{cases}
$$
$$
\sum_{i=1}^n i^2 = \frac{n(n+1)(2n+1)}{6}
$$
![[Pasted image 20230902100100.png]]

### The best properties of MGF:

$$
\frac{d^n  M_{x}(0)}{(dt)^n} = E[X^n]
$$
- $$
M_{x}(t) = E[e^{tx}]$$
- Can completely substitute [[PDF Function]]
- during [[Affine Transformation]] $M_{Y}(t)$ changes as following ($Y = a + bX$)
$$
M_{Y}(t) = \exp(at)M_{X}(bt)
$$

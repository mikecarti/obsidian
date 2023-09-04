
$$
M_{X(t)} = E(e^{tX}) =
\begin{cases}
\sum\limits_{x}e^{tX}f_{X}(x) & \text{if X discrete} \\
\int_{-\infty}^{\infty}e^{tX}  \, dx & \text{if X continuous}
\end{cases}
$$
### Definition
For many [[Distributions]], all the moments $E(X), E(X^2) \dots$ Can be encapsulated in a single function, which is called [[Moment Generating Function|moment generation function]]. It exists for many commonly used distributions and often provides 
the most efficient way to calculate moments.



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

[[Expected Value|About mean]]
# Formula
$$
sd(\mu) = \frac{\sigma}{\sqrt{ n }}
$$

# Derivation:
$$
\begin{align}
Var(\mu) = Var\left( \frac{1}{n}\sum_{i=1}^{n}x_{i} \right) = \frac{1}{n^{2}}Var\left( \sum_{i=1}^{n}x_{i} \right) =  \\
= \frac{1}{n^{2}} ( Var(x_{1}) + \dots + Var(x_{n}) ) =  \\
= \frac{nVar(X)}{n^{2}} = \frac{Var(X)}{n} = \left(  \frac{\sigma}{\sqrt{ n }}  \right)^{2}
\end{align}
$$


## Related:
[[Confidence Interval]]
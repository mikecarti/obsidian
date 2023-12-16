### Linear:
$$
a_{N}(x) = \sum_{n=1}^{N}\gamma_{n}b_{n}(x)
$$
### Mixture of experts (Linear, with non-const $\gamma$)
$$
a_{N}(x)= \sum_{n=1}^{N}\gamma_{n}(x)b_{n}(x)
$$
$\gamma_{n}(x)$ - показатель компетентности $b_n(x)$ в точке x
Hard to train.

### [[Stacking]]
$$
\begin{align}
&b_{1}(x),\dots b_{N}(x) - \text{ base models (possibly from different families)}  \\
&a(b_{1}(x), \dots, b_{N}(x)) - \text{metamodel}
\end{align}
$$

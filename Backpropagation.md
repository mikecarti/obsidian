Automatically calculates gradients.

## Notations
$$
\begin{gather}
a(x)=w_{1}x_{1}+\dots w_{n}x_{n}=f(x,w) \\
x \in \mathbb{R}^{d} \text{ - input features} \\
w \in W \text{ - weights} \\
f \text{ - arbitrary function parametrized by } w \\
\{ (x_{i}, y_{i}) \}^{n}_{i=1} \text{ - training set} \\
L(\hat{y}, y) \text{ - loss function} \\
\frac{1}{\ell}\sum_{i=1}^{\ell}L(f(x_{i}, w), y_{i}) = \mathcal{L}(w) \to \min_{w} \\
f, L \text{ - differentiable} \\
\nabla_{w} \mathcal{L}(w)
\end{gather}
$$
## Important notes
### Chain Rule
1)
$$
\begin{align}
y=f(g(x)) \\
\frac{dy}{dx}=\frac{df}{dg} \cdot \frac{dg}{dx}
\end{align}
$$
2) $$\begin{align}
y = f(g_{1}(x), g_{2}(x), \dots, g_{n}(x)) \\
\frac{dy}{dx}= \sum_{i=1}^{n}\frac{df}{dg_{i}} \cdot \frac{dg_{i}}{dx}
\end{align}
$$
### Computational Graph
$$
x_{1}^{2}+ 3()
$$
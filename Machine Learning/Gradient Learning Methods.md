## Methods:
- [[Gradient Descent|Classical Gradient Descent]]
- [[Stochastic Gradient Descent]]
- [[Stochastic Average Gradient (SAG)]]
- [[AdaGrad (Adaptive Gradient)]]
- [[Gradient Descent with Momentum]]
- [[RMSProp]]
- [[Adam Optimizer]]


$$
Q(w_{1}, \dots, w_{d}) \to \min\limits_{ w } \text{- is a loss function}
$$
Let Q be differentiable
$$
\nabla Q(w)=\begin{bmatrix}
da, \\
dw_{1}, \\
\vdots \\
\frac{dQ}{dw_{d}}
\end{bmatrix}
$$
![[Gradient#Important properties for ML]]


### Gradient Evaluation
$$
\begin{align}
Q(w)&=\frac{1}{\ell}\sum_{i=1}^{\ell}L(y_{i},a(x_{i},w)) \\
Q(w)&=\frac{1}{\ell}\sum_{i=1}^{\ell}q_{i}(w) \\
\nabla Q(w)&=\frac{1}{\ell}\sum_{i=1}^{n}\nabla q_{i}(w) \\
\ell &= 10^6 \implies 10^6\text{ gradients}  \\
&\implies \text{GD is slow}
\end{align}
$$



### Adaptive Learning Rate with Balancing Coefficient (RMSProp)
$$
\begin{align}
G_{kj} &= \alpha G_{k-1,j}+ (1-\alpha)(\nabla Q(w^{(k-1)}))^{2}_{j} \\
\end{align}
$$

Modification on [[AdaGrad (Adaptive Gradient)]] with balancing coefficient $\alpha$ for exponential fade out (kind of similar to [[Gradient Descent with Momentum]]).



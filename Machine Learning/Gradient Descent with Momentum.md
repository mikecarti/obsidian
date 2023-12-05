## Momentum (Метод инерции)
As gradient step is orthogonal to level curves, it may be sub-optimal
![[Pasted image 20230929113027.png]]

We see that along y axis they are oscillating (stupid movement), and on x axis, it moves straightforward.

h - fading average of gradients from previous steps (затухающее среднее градиентов с прошлых шагов)
$$
\begin{align}
w^{(0)} &\text{ - initialization of weights} \\
h_{0} &= 0 \text{ - momentum vector} \\
\text{step: }& \\
h_{k}&=\alpha h_{k-1} + \eta_{k}\nabla_{w}Q(w^{(k-1)}) \qquad \alpha=0.1\\ 
&\nabla_{w}Q(w^{(k-1)}) \text{ - can be changed for an estimation} \\
w^{(k)}&= w^{(k-1)} - h_{k}
\end{align}
$$

## Related:
[[Nesterov Inertion Gradient Descent]]
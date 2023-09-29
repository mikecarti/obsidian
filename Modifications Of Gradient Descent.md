## Momentum (Метод инерции)
As gradient step is orthogonal to level curves, it may be sub-optimal
![[Pasted image 20230929113027.png]]

We see that along y axis they are oscillating (stupid movement), and on x axis, it moves straightforward.

$$
\begin{align}
w^{(0)} \text{ - initialization of weights} \\
h_{0} = 0 \text{ - momentum vector} \\
\text{step: } \\
h_{k}=\alpha h_{k-1} + \xi_{k}\nabla
\end{align}
$$
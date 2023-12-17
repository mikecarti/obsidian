if $X_{t} = h(W_{t}, t)$        (and some technical assumptions)

$$
dX_{t} = \frac{ \partial h }{ \partial t } dt + \frac{ \partial h }{ \partial W_{t} }dW_{t} + \frac{1}{2}\frac{ \partial^{2} h }{ \partial W^{2}_{t} }dt 
$$

Then you can recognize if it is a [[Martingale]]
$$
dX_{t} = ? = \begin{cases}
	\dots dW_{t}  & \text{It's a margingale} \\
\dots dW_{t} + \dots  *d_{t}  &  \text{Is not a martingale}
\end{cases}
$$

#### Related:
[[Ito's Process]]
[[Stochastic Integral]]

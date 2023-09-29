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


## Adaptive Gradient (AdaGrad)
For sparse data.
$$
\begin{matrix}
\dots  & 1 & 2 & 3 & 4 & 5  & \downarrow \\
1  & 0 & 0 & 1 & 0 & 0 & \downarrow \\
2  & 1 & 0 & 0 & 0 & 0  & \downarrow \\
3  & 1 & 0 & 1 & 0 & 0  & \downarrow \\
4  & \dots & \dots & \dots & \dots & 0 & \downarrow  \\
5  & \dots & \dots & \dots & \dots & 0  & \downarrow \\
6  & \dots & \dots & \dots & \dots & 1  & \downarrow \\
7 & \dots & \dots & \dots & \dots & 1 & \downarrow 
\end{matrix}
$$

Making SGD for $<w,x>$ from top to bottom for this dataset $\eta_{k} \downarrow$
Only on seventh step i will update $w_{5}$ and $\eta_{k}$ there is small.

Let us have its own $\eta_{k}$ for every object 
$$
\begin{align}
G_{0j}&= 0 \qquad \text{j - index of feature} , k \text{ - index of step}\\
G_{kj} &= G_{k-1,j}+ (\nabla Q(w^{(k-1)}))^{2}_{j}  \text{ - how much we already trained } w_{j} \\
w^{k}_{j} &= w_{j}^{(k-1)} - \frac{\eta_{k}}{\sqrt{ G_{kj}+\epsilon }}(\nabla Q(w^{(k-1)}))_{_j}
\end{align}
$$

### Problem: 
$G_{kj}$ only grows and may stop the optimization process

Solution:
## RMSProp
$$
\begin{align}
G_{kj} &= \alpha G_{k-1,j}+ (1-\alpha)(\nabla Q(w^{(k-1)}))^{2}_{j} \\
\end{align}
$$


## Adam
Combines [[Momentum]] and [[AdaGrad]]



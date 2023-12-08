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

Making [[Stochastic Gradient Descent|SGD]] for $<w,x>$ from top to bottom for this dataset $\eta_{k} \downarrow$
Only on seventh step i will update $w_{5}$ and $\eta_{k}$ there is small.

### Adaptive Learning Rate (AdaGrad)
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
[[RMSProp]]
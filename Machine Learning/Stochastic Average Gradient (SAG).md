A good method for convex functions.

$$
Q(w)=\frac{1}{\ell}\sum_{i=1}^{\ell}q_{i}(w)
$$

$$
z_{i}^{0}=\nabla q(w^{0})
$$

SAG step:
$i_{k}~{1,\dots,\ell}$
$$
z_{i^{k}}= \begin{cases}
\nabla q_{i}(w^{(k-1)}), i =i_{k} \\
z_{i}^{(k-1)} , i\neq i_{k} 
\end{cases}
$$
$$
\nabla Q(w^{k-1})\approx \frac{1}{\ell}\sum_{i=1}^{n}z_{i}^{(k)}
w^{(k)}=w^{(k-1)} - \eta_{k}  \cdot  \frac{1}{\ell}\sum_{i=1}^{\ell}z_{i}^{(k)}
$$
$$
\mathbb{E}(Q(w^{(k)})-Q(w_{*})) = \underline{O}\left( \frac{1}{k} \right)
$$

## Why is it more effective than [[Gradient Descent]]
$q_{j}$ - error for j-th object
$Q_{j}$ - average error

$$
\nabla Q(W^{k-1}) = \frac{1}{l}\sum_{i=1}^{l}z_{i}^{(k)} = G_{k-1}
$$
Lets try to update j

$$
\nabla Q(w^{(k)}) = (lG_{k-1}-z_{j}^{(k)}+z_{j}^{(k)}) \frac{1}{l}
$$
but we need to store all $z_{j}$ that's $\underline{O}(l \cdot d)$ memory

But if we are dealing with linear model, then
$$
q_{i}(w)=L(y_{i}, <w,x_{i}>) = q_{i}(<w,x>) \in \mathbb{R}
$$ $\underline{O}(l)$ memory

## In simple terms
In SAG first iteration is calculating whole gradient, and then we change $q_{j}$ and move along average *error*


## Related
[[Modifications Of Gradient Descent]]
[[Gradient Descent]]
[[Stochastic Gradient Descent]]
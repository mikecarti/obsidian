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
## Important gradient properties
- $\nabla Q(w)$ shows direction of fastest growth in w
- $\nabla Q(w)$ is orthogonal to level curves

### Gradient Descent

![[Pasted image 20230922115033.png]]

$w^{(0)}$ - initialization 

step: 
$$
w^{(k)} = w^{(k-1)}-\eta \nabla Q(w^{(k-1)})
$$
$\eta$ - length of a step (learning rate)

stop:
	a) $|w^{(u)}-w^{k-1}| < \epsilon$
	b) $|Q(w^{(k)}-Q(w^{k-1}))|< \epsilon$
	c) $|\nabla Q(w^{(k)})|< \epsilon$
	d) k > N
	e) if error on test sample stopped dropping

### Local Minima Solutions
![[Pasted image 20230922115751.png]]

- Multi-Start
- These convergence conditions:
	a) $Q(w)$ - convex (выпуклая), дифференцируемая
	b) $\nabla Q(w)$ - [[Lipschitz Function]]
		$$
||\nabla Q(w_{1})-\nabla Q(w_{2})|| \leq L \cdot | | w_{1}-w_{2}| |
$$
	c) $\eta$ Not very large ($\eta \leq \frac{1}{L}$)
- With linear models and reasonable [[Loss Function]] $Q(w)$ is *almost* always convex (Выпуклые)
- $Q(w^{k}) - Q(w_{*})=\underline{O}\left( \frac{1}{k} \right)$ 
	k - index of iteration


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

Methods:
- [[Stochastic Gradient Descent]]
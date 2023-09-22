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
- Lots of convergence conditions
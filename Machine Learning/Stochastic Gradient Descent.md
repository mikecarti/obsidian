## Idea
Take a subset of objects, not the whole sample on every step. (One object - Stochastic, batch - Mini-Batch Gradient Descent)
$$
\nabla Q \approx \nabla q_{i}(w)
$$

step SGD:
	$i_{k}$ - random object index
	$w^k= w^{k-1}- \eta \nabla q_{i_{k}}(w^{k-1})$
	$\eta \text{ - learning rate}$
	$w^{k} \text{ - weights at step k}$
	$q_{i_{k}} \text{ - loss function of i-th object for k-th step}$

### Problem:
If $||w^{(k)}-w_{*}|| \gg 0$,
then $\nabla Q(w) \approx \nabla q_{i}(w)$

If $||w^{(k)}-w_{*}|| \approx 0$,
then $\nabla Q(w) \neq \nabla q_{i}(w)$

### Solution:
Take a decreasing function as a learning rate ($\eta$)

##### Robinson Manro Condition:
$$
\begin{align}

\sum_{i=1}^{\infty}(\eta_{k})&=\infty \\
\sum_{i=1}^{\infty}(\eta_{k})^2 &< \infty  \\
&\implies SGD \text{ Converges}
\end{align}
$$

### Speed of convergence:
$$
\mathbb{E}(Q(w^{k}) - Q(w_{*})= \underline{O}\left( \frac{1}{\sqrt{ k }} \right)
$$

Notes: 
1) Mini-Batch GD
$$
\nabla Q(w)\approx \frac{1}{t}\sum_{j=1}^{t}\nabla q_{ij}(w)
$$
2) SGD is good for [[On-line learning]]
When there is not enough storage to store the whole sample.
When RAM can't comprehend such a large sample.
![[Pasted image 20230922122354.png]]



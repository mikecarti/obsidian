$$
\nabla Q \approx \nabla q_{i}(w)
$$

step SGD:
	$i_{k}$ - random object index
	$w^k= w^{k-1}- \eta \nabla q_{i_{k}}(w^{k-1})$

### Problem:
If $||w^{(k)}-w_{*}|| \gg 0$,
then $\nabla Q(w) \approx \nabla q_{i}(w)$

If $||w^{(k)}-w_{*}|| \approx 0$,
then $\nabla Q(w) \neq \nabla q_{i}(w)$

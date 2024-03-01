# Isolation Forest (IF)
Idea: if object is close to root in [[Random Forest]] then it is an anomaly
![[Pasted image 20240216121859.png]]

## Training
- build N trees
- random predicates in every tree (feature $j$ from [[Uniform Distribution]] on features, threshold $t \sim U[x_{j}^{min}, x_{j}^{\max_{}}]$)
- stop building, if:
	1) leaf contains only 1 object
	2) maximum depth is reached D (D $= \log_{2}l$)

## Inference
x - new observation
$b_{n}(x)$ - distance in n-th tree, from root to the leaf, where x came.
(Also account how many training objects remain):
$$
\text{Anomaly Score: } \quad   h_{n}(x) = b_{n}(x) + c(m)
$$
$m$ - number of objects from training set, that got in the same node as $x$.
$c(m)$ - average length of path from root to leaf in [[Binary Search Tree]] (estimate of possible splitting if tree building was not stopped)

There is a nice estimate for $c(m)$:
$$
\begin{align}
&c(m) = 2H(m-1)-\frac{2{m-1}}{m} \\
&H(i) = \ln(i) + 0.572 \text{ - i-th harmonic number} \\ \\
&\text{More practically} \\
&c(m) = \log_{2}(m)
\end{align}
$$
$$
a(x) = 2^{-\frac{\frac{1}{N}\sum_{n=1}^{N}h_{n}(x)}{c(l)}}
$$
The bigger $a(x)$ -> the more anomalous x.


![[Pasted image 20240301145718.png]]
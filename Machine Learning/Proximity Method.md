Method that helps to optimize functions that have 2 parts:
1) differential
2) non-differential but convex


$$
\begin{align}
w^{(k)} = S_{\eta\alpha}(w^{(k-1)}-\eta \nabla_{w}Q(w^{(k-1)})) \\
S_{\eta\alpha}(w_{i}) = \begin{cases}
w_{i} - \eta \alpha & w_{i} \geq \eta\alpha \\
0, & \lvert w_{i} \rvert < \eta\alpha \\
w_{i} + \eta\alpha , & w_{i} \leq - \eta\alpha 
\end{cases}
 \\
\end{align}
$$
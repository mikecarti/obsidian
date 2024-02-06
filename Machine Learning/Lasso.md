L1 Regularization
$$
R(w) = \lvert \lvert w \rvert  \rvert_{1}= \sum_{i=1}^{n}\lvert w_{j} \rvert
$$

### Adaptive LASSO:
$$
\begin{align}
RSS + \lambda \sum_{j=1}^{k} W_{j} \; \cdot  \mid \beta_{j}\mid \to \min_{\beta_{j}} \\
W_{j} = \frac{1}{\mid\hat{\beta}_{j}^{c}\mid}
\end{align}
$$
$\hat{B}_{j}^{c}$ is some [[Consistent Estimator]] of $\beta_{j}$.

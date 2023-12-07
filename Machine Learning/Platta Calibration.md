$b(x)$ - model
$$
\begin{align}
c(x) = \frac{1}{1+\exp(\alpha b(x)+ \beta)} = \mathbb{P}(y=+1\mid x) \\
-\sum_{i=1}^{l}\left( \left[ y_{i}=+1 \right] \log c(x) + \left[ y_{i}=-1 \right] \log(1-c(x_{i}))  \right) \to \min_{\alpha,\beta \, \in \, R} 
\end{align}
$$

Important: $\alpha, \beta$ should be fitted **not** on training data.
Second line is [[Cross Entropy Loss (Log Loss)]]


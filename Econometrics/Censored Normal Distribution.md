![[Pasted image 20240229134437.png|500]]

$y^{*} \sim \mathcal{N}(\mu, \sigma^{2})$
$$
y = \begin{cases}
\alpha, y^{*} \leq a \\
y^{*}, y^{*} > a
\end{cases}
$$
$$
\begin{align} 
&\alpha \text{ - point of truncation} \\
&E(y)= \phi(\alpha)  \cdot \alpha + (1-\phi(\alpha))(\mu + \sigma\lambda) \\
&V(y) = \sigma^{2}(1-\phi(\alpha))[(1-\delta)+(\alpha - \lambda)^{2}  \cdot  \phi(\alpha)] \\
&\lambda = \frac{\phi(\alpha)}{1-\phi(\alpha)} \quad \quad \delta = \lambda^{2} - \lambda\alpha
\end{align}
$$


![](https://i.stack.imgur.com/BRZwM.png)

$$
\begin{align}
&E(x\mid \text{truncation}) = \mu  + \sigma \cdot \lambda(\alpha) \quad \quad \alpha - \text{point of truncation} \\
&V(X \mid \text{truncation}) = \sigma^{2}[1-\delta(\alpha)] \quad \quad \alpha \text{ is standardized } \left( \alpha = \frac{{\alpha^{*}-\mu}}{\sigma} \right)\\
&\lambda(\alpha) = \frac{\phi(\alpha)}{1- \phi(\alpha)}, \text{if truncation is } x > \alpha \\
&\lambda(\alpha) = \frac{{-\phi (\alpha)}}{\phi(\alpha)}, \text{if truncation is } x <\alpha \\
&\delta(\alpha) = \frac{\lambda(\alpha)}{\lambda(\alpha)-\alpha}
\end{align}   
$$
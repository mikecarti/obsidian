Train mode:
$$
\begin{align}
& x \in \mathbb{R}^{B\times N} \quad x_{i}\in \mathbb{R}^{N}\\
& \mu = \frac{1}{B}\sum_{i=1}^{B}x_{i} \quad x_{i} \text{ - vector}\\
& \sigma^{2} = \frac{1}{B}\sum_{i=1}^{B}(x_{i}-\mu)^{2} \quad \sigma^{2} \text{ - vector}\\
& \hat{x}_{i} = \frac{{x_{i} - \mu}}{\sqrt{ \sigma^{2}+\epsilon }} \quad \epsilon \text{ - for not getting 0 denom.} \\
&\frac{1}{B}\sum_{i=1}^{B}\hat{x}_{i}^{2} = 1  \\
&y_{i} = x_{i} \odot w + \beta \qquad w,\beta\in \mathbb{R}^{N} \\

\end{align}
$$
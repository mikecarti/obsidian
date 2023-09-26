$$
\begin{align}
\lim_{ n \to \infty }\mathbb{P}(|\bar{x}_{n}-\mu| > \epsilon) = 0. \quad \forall \epsilon >0  
\end{align}
$$

## Proof:

$$
\begin{align}
\text{set of iid } x_{i} : \\
\mathbb{E}(X) = \mu \\
\{ X_{n} \} \qquad X_{n} = \frac{1}{n}\sum_{i=1}^{n}x_{i}  \\ \\

\lim_{ n \to \infty }\bar{X}_{n}= \mu\\
x_{1}, x_{2}, \dots, x_{100500} \\
\bar{x}_{1} = x_{1} \\
\bar{x}_{2} = \frac{{x_{1}+x_{2}}}{2} \\
\vdots \\
\bar{x}_{N} = \frac{{x_{1} + \dots + x_{N}}}{N}
\end{align}
$$
$$
\begin{align}
\lim_{ n \to \infty }\mathbb{P}(|\bar{x}_{n}-\mu| > \epsilon) = 0. \quad \forall \epsilon >0  
\end{align}
$$
1) find a limit (in this task it is given $\mu$)
2) prove by definition
According to [[Chebyshev's Inequality]] :
$$
\begin{align}
\lim_{ n \to \infty } \mathbb{P}(|\bar{X}_{n}-\mu|>\epsilon) &\leq \lim_{ n \to \infty } { \frac{Var (\bar{X}_{n})}{\epsilon^{2}}} \\
Var\left( \frac{1}{n}\sum_{i=1}^{n}x_{i} \right) &= \frac{1}{n^{2}}Var(X_{1}+\dots+X_{n})= \qquad  x_{i} - i.i.d \\ 
= \frac{1}{n^{2}} \cdot n \cdot \sigma^{2}&=\frac{\sigma^{2}}{n} \implies \text{by substituting into upper eq} \\
\lim_{ n \to \infty } \frac{\sigma^{2}}{n\epsilon^{2}} &= 0 \implies \text{therefore} \\
\lim_{ n \to \infty } \mathbb{P}(|\bar{X}_{n}-\mu|>\epsilon) &\leq 0
\end{align}
$$

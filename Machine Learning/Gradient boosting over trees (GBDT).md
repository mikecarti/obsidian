$$
\begin{align}
b_{n}(x)= \sum_{j=1}^{\mathcal{J}_{n}} \underbrace{ b_{nj} }_{ \text{pred in j-th leaf} }\left[ x \, \in \, \underbrace{ R_{nj} }_{ \mathbb{X} \text{ to j-th leaf of a tree} } \right]  \\
a_{N}(x) = a_{N-1}(x) + \sum_{j=1}^{\mathcal{J}}b_{Nj}\left[ x \, \in \, R_{Nj} \right]  
\end{align}
$$

Idea: let's find $b_{Nj}$, so they would be optimal w.r.t $L(y,z)$
$$
\begin{align}
\sum_{i=1}^{l}L\left( y_{i},a_{N-1}(x_{i}) + \sum_{j=1}^{\mathcal{J}_{N}}\gamma_{j}\left[ x_{i} \, \in \, R_{Nj} \right]  \right) \to \min_{\gamma_{1}, \dots,} \\
\sum_{j=1}^{\mathcal{J}_{N}}\sum_{(x_{i,} y_{i}) \, \in \, R_{Nj}} L(y_{i}, R_{N-1}(x_{i})+\gamma_{j}) \to \min_{\gamma_{1}, \dots} \\
\text{Task is splitted on } \mathcal{J}_{N} \text{ sub-tasks}: \\
\sum_{(x_{i,} y_{i}) \, \in \, R_{Nj}} L(y_{i}, R_{N-1}(x_{i})+\gamma_{j})
\end{align}
$$

### Example:
$$
\begin{align}
L(y,z) = \log(1+\exp(-yz)) \\
\sum_{(x_{i}, y_{i}) \, \in \, R_{Nj}}\log(1+\exp(-y_{i} \cdot a_{N-1}(x_{i})+\gamma_{j})) \to \min_{\gamma_{j}} \\
\end{align}
$$
Make 1 step of [[Newton-Rafson Method]] from point $\gamma=0$
$$
\gamma_{j} = -\frac{{\sum_{(x_{i},y_{i})\, \in \,R_{Nj}}s_{j}}}{\dots}
$$


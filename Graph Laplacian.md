# Definition

$$
\begin{align}
&D = diag(d_{1}, \dots, d_{l}) \\
&d_{i} -\text{ degree of node } x_{i} \\
&d_{i} = \sum_{j=1}^{l}\underbrace{ w_{ij}  }_{ \text{edge w} } \\
&W = (w_{ij})^{l}_{i,j} - \text{ Adjacency matrix }
\end{align}
$$

THEN Laplacian $L$ is defined as:
$$
L = D -W
$$

# Properties
1) 
$f \, \in \, \mathbb{R}^{l}$
$$
f^{T}Lf = \frac{1}{2}\sum_{i,j=1}^{l}w_{ij}(f_{i}-f_{j})^{2}
$$
2) $L$ - [[Symmetric Non-negatively Definite Matrix]]

## Theorem 
L - Laplacian $G$, then:
1) [[Eigenvalue]] $\lambda=0$ in $L$ has multiple equal to adjacency components $G$ ([[Компонента связанности]])
2) Let $\mathcal{A}_{1}, \dots, \mathcal{A}_{k}$ - adjacency components of $G$ ([[Компонента связанности|Компоненты связанности]]).
Then: vectors $f_{1}, \dots,f_{k}$ , where $f_{i} = ([x_{j} \, \in \,\mathcal{A}_{i}])^{l}_{j=1}$
Are [[Eigenvector]]s, that correspond to their own [[Eigenvalue]]s

# Hypothesis
Let $x_{i}, x_{k}$ - similar objects, that is $\rho(x_{i}, x_{k}) \approx 0$
Then we assume that [[Eigenvector]] $f_{j}$ that corresponds to small [[Eigenvalue]], it is fulfilled that $f_{ji}\approx f_{jk}$ 


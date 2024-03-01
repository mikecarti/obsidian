$$
\begin{align}
&C^{i}= \{ \{ x_{1} \}, \dots, \{ x_{l} \} \} \\
&C^{j}= \{ x_{1}, \dots, X_{l-j+1}\} \\
&(m,n) = \operatorname*{argmin}_{1\leq m\leq n\leq l-j+1}  \\
&d(X_{m}, X_{n}) - \text{measure of cluster closeness} \\
&C^{j+1} = \left( C^{j}\setminus \{ X_{m},X_{n} \} \right) \cup \{X_{m}\cup X_{n}   \}  \\
&C^{l}=\{ \{ x_{1},\dots,x_{l} \} \}
\end{align}
$$

![[Pasted image 20231216165523.png]]
is a [[Dendrogram]]
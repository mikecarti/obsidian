Also known as Log Loss 
$$
\begin{align}
&(\underbrace{ z }_{ \text{logits} }, y) \\
&\text{cross-entropy: } \{ p_{i} \}_{i=1}^{c}, \{ q_{i} \}_{i=1}^{c} \text{ - arbitrary distributions} \\
&= - \sum_{i=1}^{c}q_{i}\log p_{i} \quad q_{i}=[i=y]
\end{align}
$$

![[Pasted image 20231006165553.png]]


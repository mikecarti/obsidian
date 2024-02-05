## Final Layer
- [[Sigmoid]]
- [[SoftMax]]

## In-Between Layer
- [[RELU (Rectified Linear Unit)]]
- [[Leaky RELU]]
- [[Hyperbolic Functions]]

## Importance

Given $z_{i}$ - i-th layer, $W_{i}$ - matrix of weights
$$
\begin{gather}
x \in \mathbb{R}^{d_{0}}  \\
a(x) = <w,x> = w^Tx, w \in \mathbb{R}^{d_{0}} \\
z_{1}=W_{1}x \qquad W_{1} \in \mathbb{R}^{d_{1} \times d_{0}} \\
z_{2} = W_{2}z_{1} \qquad W_{2} \in \mathbb{R}^{d_{2} \times d_{1}} \\
\dots \\
z_{n} = W_{n}z_{n-1} \qquad W_{n}\in \mathbb{R}^{d_{n} \times d_{n-1}} \\ \\
z_{n} = \underbrace{ W_{n}W_{n-1}\dots W_{2}W_{1}x }_{ W \in \mathbb{R}^{d_{n} \times d_{0}} } \\ \\
\text{THat shit is linear as hell, lets add non-lin.} \\ \\
\sigma( \cdot ) : \mathbb{R}\to \mathbb{R} \text{ - activation func.} \\
z_{i} = \sigma(\underbrace{ W_{i}z_{i-1}+ b_i }_{ \text{ Linear Layer} }) \qquad b_{i} \in \mathbb{R}^{di}
\end{gather}
$$

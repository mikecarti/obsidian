Randomly zeros out elements of the input tensor during training.

$$
\begin{align}
&x \in \mathbb{R}^{B\times N} \qquad \text{ B - batch size. N - num of neurons in hidd. layer}  \\
&m \in \mathbb{R}^{B\times N} \qquad m_{ij} \in {0,1} \qquad m_{ij} \sim Bernolli(1-p) \\
&y = m \odot x \qquad \text{element-wise product} \\
&\mathbb{E}[y] = \mathbb{E}[m \odot x] = \mathbb{E}[m]\odot x = (1-p)x
\end{align}
$$
Therefore we can see, that we multiply previous layer by $(1-p)$ and therefore we need to normalize the output.

Train mode:
$$
\begin{align}
m_{ij} \sim Bernoulli(1-p) \\
y = m \odot x \cdot  \frac{1}{1-p}
\end{align}
$$
Eval mode / Inference mode:
$$
y = x 
$$

## Related:
[[Neural Network]]
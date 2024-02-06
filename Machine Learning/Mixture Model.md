(Смесь распределений)

# PDF
$$
p(x) = \sum_{k=1}^{K} \pi_{k}p_{k}(x)
$$
$\pi_{k}\geq 0$     $\sum_{k=1}^{K}\pi_{k}=1$

## Another way for PDF
$$
\begin{align}
&z = (z_{1},\dots,z_{k}) \text{ - hidden binary variables} \\
&\sum_{k=1}^{K}z_{k}=1 \\
&p(x,z) = \prod_{k=1}^{K}(\pi_{k}p_{k}(x))^{z_{k}} \\
&\sum_{z}p(x,z) = \sum_{k=1}^{K}\pi_{k}p_{k}(x) = p(x) \\
\end{align}
$$




## Normal distributions
$$
p(x)=\sum_{k=1}^{K}\pi_{k}\mathcal{N}(x\mid \mu_{k}, \Sigma_{k})
$$

## [[Maximum Likelihood Estimation (MLE)]]:
$$
\sum_{i=1}^{l}\sum_{k=1}^{K}\Big(z_{k}\log \pi_{k} + z_{k}\log p_{k}(x_{i})\Big)\to \max_{\pi_{k}, \mu_{k}, \Sigma_{k}, z_{k}}
$$

# Statement 1
For Gaussian Mixture holds:
$$
\theta^{i+1}-\theta^{i}=P^{i} \cdot \nabla_{\theta}\log p(X\mid \theta^{i}) \quad  \text{(in EM)}
$$
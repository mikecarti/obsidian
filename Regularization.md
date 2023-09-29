#### Famous experimental fact: 
If a linear model is over-trained $<==>$ it has large weights.

#### Why?

1. Imagine we have some linearly dependent features
$$
\begin{align}
\exists v \in \mathbb{R}^{d}: \forall x \in \mathbb{X} \qquad <u, x> = 0 \\
w_{ \cdot } - \text{solution} \qquad \frac{1}{l}\sum_{i=1}^{l}(<w,x>-y_{i})^{2 } \to min \\
<w_{*} + \alpha u, x> = <w_{*}, x> + \alpha <v, x> = <w_{*}, x> \\
\text{therefore } w_{*} + \alpha v - solutio
\end{align}

$$

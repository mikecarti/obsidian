![[Pasted image 20230929174713.png]]
$$
LeakyRELU(x) = \begin{cases}
x & x > 0 \\
\alpha x  & x \leq 0
\end{cases}
$$

By never setting the gradients to zero, it allows every parameter of the model to keep learning.

Although it is piecewise linear, it is enough non-linearity to not collapse all matrices in one in a [[Neural Network]].

$\alpha$ is a hyper-parameter.
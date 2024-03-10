## [[Dummy Variable]]
$$
y_{i} = (1-x_{i})y_{i}(0) + x_{i}y_{i}(1)
$$

Where $x_{i}$ is the [[Dummy Variable]] and $y_{i}(0), y_{i}(1)$ are the corresponding values from both experiments. (Control group and test group)

Now, assuming (unrealistically) constant treatment effect, it can be rewrited:
$$
\begin{align}
y_{i}(1) = \tau + y_{i}(0) \\
y_{i} = y_{i}(0) + \tau x_{i} \\
y_{i} = \alpha_{0} + \tau x_{i} + u_{i}(0)
\end{align}
$$

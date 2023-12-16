Other way of model composing. 


$$
\begin{align}
&b_{1}(x),\dots b_{N}(x) - \text{ base models (possibly from different families)}  \\
&a(b_{1}(x), \dots, b_{N}(x)) - \text{metamodel}
\end{align}
$$

If $a$ and $b_{1}, \dots b_{N}$ are trained on the same subset, then it will overfit. Base models have to be trained one by one (not together at once as in [[Neural Network]]). 

$$
\begin{align}
X= X_{1}\cup\dots \cup X_{k} \\
\sum_{k=1}^{J}\sum_{(x_{i}, y_{i}) \, \in \, X_{k}} L(y_{i}, a\left( b_{1}^{-k} (x_{i}), \dots, b_{N}^{-k}(x_{i}) \right) )\to \min_{a} \\
b_{n}^{-k}(x) = b_{n}(x)\text{, trained on } X\setminus X_{k}
\end{align}
$$
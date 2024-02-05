
Provides a way for computers to calculate derivatives of neural networks [[Loss Function|loss functions]] fast.


## Examples
#1

$$
\begin{align}
z_{1} = f_{1}(x, w_{1}) \\
z_{2} = f_{2}(z_{1}, w_{2}) \\
\dots \\
z_{n} = f_{n}(z_{n-1}, w_{n}) \\
\hat{y}=g(z_{n})  \\
\ell = L(\hat{y}, y)
\end{align}
$$
![[Pasted image 20230929172340.png| 500]] 

#2
$$
\begin{align}
y = f(x_{1},x_{2},x_{3}) = x_{1}^{2} + 3(x_{2} \cdot x_{3} - x_{1}^{2}) \\
\text{Compute: } \frac{ \partial y }{ \partial x }  \\
 \\
x_{1}=1, \quad x_{2}=2, \quad x_{3}=3
\end{align}
$$
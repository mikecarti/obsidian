Automatically calculates gradients.

## Notations
$$
\begin{gather}
a(x)=w_{1}x_{1}+\dots w_{n}x_{n}=f(x,w) \\
x \in \mathbb{R}^{d} \text{ - input features} \\
w \in W \text{ - weights} \\
f \text{ - arbitrary function parametrized by } w \\
\{ (x_{i}, y_{i}) \}^{n}_{i=1} \text{ - training set} \\
L(\hat{y}, y) \text{ - loss function} \\
\frac{1}{\ell}\sum_{i=1}^{\ell}L(f(x_{i}, w), y_{i}) = \mathcal{L}(w) \to \min_{w} \\
f, L \text{ - differentiable} \\
\nabla_{w} \mathcal{L}(w)
\end{gather}
$$
## Important notes
### Chain Rule
#### 1)
$$
\begin{align}
y=f(g(x)) \\
\frac{dy}{dx}=\frac{df}{dg} \cdot \frac{dg}{dx}
\end{align}
$$
#### 2) 
$$\begin{align}
y = f(g_{1}(x), g_{2}(x), \dots, g_{n}(x)) \\
\frac{dy}{dx}= \sum_{i=1}^{n}\frac{df}{dg_{i}} \cdot \frac{dg_{i}}{dx}
\end{align}
$$
### Computational Graph
$$
\begin{align}
x_{1}^{2}+ 3(x_{2} \cdot x_{3}-x_{1}^{2}) = f(x_{1},x_{2},x_{3}) \\
x_{1} = 1, x_{2}=2, x_{3}=3 \\
\frac{\delta f}{\delta x_{i}}
\end{align}
$$
![[Pasted image 20230929170113.png|400]]
$$
\begin{align}
&z_{1} = x_{1}^{2} \\
&z_{2} = x_{2} \cdot x_{3} \\
&z_{3}=z_{2}-z_{1} \\ 
&z_{4} = 3z_{3} \\
&y = z_{5} = z_{1} + z_{4}
\end{align}
$$
$$
\begin{align} 
\frac{dy}{d x_{i}} = ? \\
\frac{dy}{dy} =1 \\
\frac{dy}{dz_{4}} = \frac{dy}{dy} \cdot \frac{dy}{dz_{4}}= 1 \cdot 1 = 1 \\
\frac{dy}{dz_{3}} = \frac{dy}{dz_{4}} \cdot \frac{dz_{4}}{dz_{3}} = 1 \cdot  3 = 3  \\
\frac{dy}{dz_{1}}= \frac{dy}{dy} \left(  \frac{dz_{1}}{dz_{4}} \right)  \cdot \frac{dy}{dz_{3}} \cdot \frac{dz_{3}}{dz_{1}} = -2 \\
\frac{dy}{dz_{2}}=\frac{dy}{dz_{3}
\end{align}
$$
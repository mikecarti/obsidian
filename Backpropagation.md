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
\begin{gather}
x_{1}^{2}+ 3(x_{2} \cdot x_{3}-x_{1}^{2}) = f(x_{1},x_{2},x_{3}) \\
x_{1} = 1, x_{2}=2, x_{3}=3 \\
\frac{\delta f}{\delta x_{i}} = ?
\end{gather}
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
\frac{dy}{dz_{2}}=\frac{dy}{dz_{3}}=3 \\
\frac{dy}{dx_{1}} = \frac{dy}{dz_{1}} \cdot \frac{dz_{1}}{dx_{1}}=-2  \cdot  2x_{1}=-4 \\
\frac{dy}{dx_{2}}=\frac{dy}{dz_{2}} \cdot \frac{dz_{2}}{dx_{2}}=3 \cdot x_{3}=9 \\
\frac{dy}{dx_{3}}=\frac{dy}{dz_{2}} \cdot \frac{dz_{2}}{dx_{3}}=3 \cdot x_{2}=6
\end{align}
$$
$$
\begin{align}
x \qquad  \\
z_{1} = f_{1}(x, w_{1}) \\
z_{2} = f_{2}(z_{1}, w_{2}) \\
\dots \\
z_{n} = f_{n}(z_{n-1}, w_{n}) \\
\hat{y}=g(z_{n})  \\
\ell = L(\hat{y}, y)
\end{align}
$$
![[Pasted image 20230929172340.png]]


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

![[Pasted image 20230929173104.png]]

$z_{i} \text{ - latent representation (fully-connected layer)}$
$z_{i}=\underbrace{( z^{(1)}_{1}, \dots, z_{i}^{(d_{i})} )}_{ neurons }$  Multi-layer perceptron (MLP) or Fully-Connected network (FCN)





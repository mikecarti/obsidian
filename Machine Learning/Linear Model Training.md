$$
\frac{1}{\ell}\sum_{i=1}^{\ell}(<w,x_{i}>-y_{i})^2 \to \min\limits_{w \in R^d}
$$
$$
X = \begin{bmatrix}
x_{11} & \dots & x_{1d} \\
\vdots & \vdots & \vdots \\
x_{\ell1} & \dots  & x_{x_{\ell d}}
\end{bmatrix}
$$

$$
X_{w}=\begin{bmatrix}
<w,x_{1}> \\
\vdots \\
<w,x_{\ell}>
\end{bmatrix}
$$
$$
\begin{align} 
Q(w)=\frac{1}{\ell}\mid\mid Xw-y\mid\mid^2_{2}\to min \\
\nabla Q(w)=0 \\
w_{*}=(X^TX)^{-1}X^Ty
\end{align}
$$

## Problems:
1) Not invertible matrix (degenerate, singular, вырожденная)
2) Matrix inversion $\underline{O}(d^3)$
3) If $L(y,z)$ is a tricky function, then $\nabla Q(w)=0$ is not solvable

## Solution:
[[Gradient Learning Methods]]

## Related:
[[Linear Regression]]
$\mathbb{Y} = \{ -1, +1 \}$
-1: negative class
+1: positive class

$a(x) = sign<w,x>$

### Geometry
$<w,x> = 0$    - eq. of hyperplane
$w$ - вектор нормали (orthogonal vector)
$\mid<w,x> \mid$ - distance from separating hyper-plane (confidence of model)

![[Pasted image 20231006121359.png]]

## Loss Function
$$
\begin{align}
Q(a) = \frac{1}{\ell}\sum_{i=1}^{\ell}[a(x_{i})\neq y_{i}] \quad - \text{  error rate} \\
\frac{1}{\ell}\sum_{i=1}^{\ell}[sign<w,x_{i}> \neq y_{i} ]
\end{align}
$$
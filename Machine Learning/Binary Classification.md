$\mathbb{Y} = \{ -1, +1 \}$
-1: negative class
+1: positive class

$a(x) = sign<w,x>$

### Classification non-differentiable loss function:
$$
\begin{align}
arg\min_{b\, \in \,\left[ 0,1 \right] } \frac{1}{n}\sum_{i=1}^{n}L(y_{i},b) = \frac{1}{n}\sum_{i=1}^{n}\left[ y_{i}=+1 \right] 
\end{align}
$$

### Geometry
$<w,x> = 0$    - eq. of hyperplane
$w$ - вектор нормали (orthogonal vector)
$\mid<w,x> \mid$ - distance from separating hyper-plane (confidence of model)

![[Pasted image 20231006121359.png]]

## [[Loss Function]]
$$
\begin{gather}
Q(a) = \frac{1}{\ell}\sum_{i=1}^{\ell}[a(x_{i})\neq y_{i}] \quad - \text{  error rate} \\
\frac{1}{\ell}\sum_{i=1}^{\ell}[sign  \langle w,x_{i} \rangle  \neq y_{i}] \to \min_{w} \quad \text{NP-complete task..} \\
= \frac{1}{\ell}\sum_{i=1}^{\ell}[y_{i} \langle  w,x_{i}\rangle  \;\;< 0] \qquad y_{i} = \pm1 \quad y_{i}\langle w,x_{i}  \rangle  = sign \langle w, x_{i} \rangle  \\
M_{i} = y_{i} \langle  w,x_{i}\rangle  \text{ - margin} \\
sign(M_{i}) \text{ - classification truthness} \\
\mid M_{i}\mid \text{- confidence}
\end{gather}
$$

therefore for now we use this loss function:
$$
L(M) = [M<0] \text{ - threshold loss function}
$$
![[Pasted image 20231006122545.png |450]]

Lets try to change this function so ball would start rolling

![[Pasted image 20231006122644.png | 450]]

### Idea:
$$
\begin{gather}
(M < 0 ) \leq \hat{L}(M) \text{ - diff. upper estimation} \\
0 \leq \frac{1}{\ell}\sum_{i=1}^{\ell}[y_{i} \langle w,x_{i} \rangle  < 0] \leq \frac{1}{\ell}\sum_{i=1}^{\ell}\hat{L}(y_{i} \langle w,x_{i} \rangle ) \to \min \\
\hat{L}_{1}(M) = max(0, 1 - M) \text{ - hinge loss} \\
\hat{L_{2}}(M) = \log(1+\exp(-M))  \\
\hat{L_{3}} = e^{-M} \\
\hat{L_{4}}= \dots \\
\dots \\
\frac{1}{\ell}\sum_{i=1}^{\ell}\hat{L}(y_{i}\langle  w,x_{i} \rangle ) + \alpha R(w) \to \min_{w} \\
\text{And use gradient descent}
\end{gather}
$$

By this diff. upper estimation i mean:
$$
\frac{1}{l}\sum_{i=1}^{l}\left[ sign \left< w,x \right> \neq y_{i} \right]  \leq \frac{1}{l}\sum_{i=1}^{l}\tilde{L})(y_{i}\left< w,x_{i} \right> )\to \min_{w} 
$$

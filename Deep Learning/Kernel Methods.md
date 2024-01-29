## Intuition:
Add a lot of non-linear features and brute force your way to good performance.

![[Pasted image 20240112145442.png]]

$$
x_{3} = x_{1}^{2} + x_{2}^{2}
$$
![[Pasted image 20240112145523.png]]

### For example:
$$
x_{1},\dots x_{d} \to x_{1}^{2},\dots,x_{d}^{2}
$$
$$
x_{1},\dots x_{d} \to \log(\mid x_{1}\mid +1), \dots, \log(\mid x_{d}\mid +1)
$$
### Addition of Non-Linear Features
+Quality raises
-Too much features (**hard to calculate**, overfitting)

## In General:
$$
\begin{align}
&\Big[\frac{1}{2} \lvert\lvert \Phi w-y \rvert\rvert ^{2}+\lambda \lvert\lvert w \rvert\rvert ^{2}\to \min_{} \Big] \xRightarrow[]{\Phi\to K=\Phi \Phi^{-1}} \begin{cases}
\frac{1}{2} \lvert\lvert K\alpha - y\rvert\rvert^{2}+\frac{\lambda}{2}\alpha^{T}K\alpha  \to \min_{\alpha}  \\ 
 a(x) = \sum_{i=1}^{n}\alpha_{i}\left< x,x_{i} \right> \\
\alpha \text{ is some vector of new weights}
\end{cases} \implies \\
&\xRightarrow[\text{Kernel Trick}]{\left< x,z \right>\to K(x,z)=\left< \phi(x),\phi(z) \right> }  \begin{cases}
K(x,z) \text{  - kernel} \quad  \\
 K=\left( K(x_{i}, x_{j}) \right)_{i,j=1}^{l} \\
 \frac{1}{2}\lvert\lvert K\alpha-y  \rvert\rvert^{2} + \frac{\lambda}{2}\alpha^{T}K\alpha\to \min_{} \\
a(x)=\sum_{i=1}^{l} \alpha_{i}K(x,x_{i})
\end{cases}
\end{align}
$$

## Theory
### Dual representation for [[Linear Regression]]
$$
a(x)= \sum_{j=1}^{m}w_{j}\mu_{j}(x)
$$
$\mu_{j}(x)$ - basis function (new features {$x^{2}, \sqrt{x  }$})
$$
Q(w) = \frac{1}{2}\sum_{i=1}^{l}\left( \sum_{j=1}^{m}w_{j}\mu_{j}(x_{i}) -y_{i} \right)^{2} + \frac{\lambda}{2}\lvert\lvert w \rvert\rvert^{2} \to \min_{w}  
$$
$$
\Phi = \begin{bmatrix}
\mu_{1}(x_{1})\dots\mu_{m}(x_{1}) \\
\dots \\
\mu_{1}(x_{l}) \dots \mu_{m}(x_{l})
\end{bmatrix} \, \in \,\mathbb{R}^{l\times m}
$$
$$
Q(w) = \frac{1}{2}\lvert\lvert \Phi w - y \rvert\rvert^{2} + \frac{\lambda}{2} \lvert\lvert w \rvert\rvert^{w} \to \min_{_{w}}  
$$
$$
\begin{align}
\nabla Q(w) &= \Phi^{T}(\Phi w-y) +\lambda w = 0 \\
w&=-\frac{1}{\lambda}\Phi^{T}(\Phi w - y) \implies \text{Optimal } w \text{ has to look like } w = \Phi^{T}a  \\
&\text{Then make substitution}: w= \Phi^{T}a \\
Q(a)&=\frac{1}{2}\lvert\lvert \Phi\Phi^{T}a-y \rvert\rvert ^{2} + \frac{\lambda}{2}a^{T}\Phi \Phi^{T}a \to \min_{a}  \\
\Phi\Phi^{T} &- \text{Gramm Matrix}
\end{align}
$$
[[Gramm Matrix]]
$$
\begin{align}
K= \Phi\Phi^{T} = (\left< \mu(x_{i}),\mu (x_{j}) \right> )^{l}_{i,j=1} \, \in \,R^{l\times l} \\
\end{align}
$$
Size of k is not dependent on number of features!
Therefore given effectively found Gramm Matrix 
(Without using all features in explicit form)
Then complexity of training the model will not depend
on number of features!

$$
a = \left( K+\lambda I \right) ^{-1}y
$$
## Kernels
#### Merser Kernel
That is a 
$$
\begin{align}
K(x,z)= \left< \mu(x), \mu(z) \right>  \\
x,z \, \in \,\mathbb{X} \\
\mu:\mathbb{X}\to H
\end{align}
$$
H - спрямляющее пространство 
$\mu(x)$ -  спрямляющее преобразование

### Example:
$x = (x_{1},\dots,x_{d})\, \in \,\mathbb{R}^{d}$
$$
\begin{align}
\mu(x)= (x_{i}x_{j})^{d}_{i,j=1} \, \in \, \mathbb{R}^{d^{2}} \\
K(x,z)= \left< \mu(x), \mu(z) \right> = \left< (x_{i}xj)^{d}_{i,j=1},\left( z_{i}z_{j} \right) ^{d}_{i,j=1} \right> = \\
=\sum_{i=1}^{d}\sum_{j=1}^{d}x_{i}x_{j}z_{i}z_{j} = \underbrace{ \sum_{i=1}^{d}x_{i}z_{i} }_{ \left< x,z \right>  }\underbrace{ \sum_{i=j}^{d}x_{j}z_{j} }_{ \left< x,z \right>  } =\left< x,z \right>^{2} - \\
 - \text{which is much easier to calculate}
\end{align}
$$
Idea: sometimes scalar product $K(x,z)$ can be counted without calculating $\mu(x)$.

## Implicit (Неявное) задание ядер
We want to take some $K(x,z)$, not knowing $\mu(x)$, but knowing that it is a kernel. 
$$
\begin{align}
K(x,z)= \sin(\left< x,z \right> ) + e^{\left< x,z \right> } \text{ - kernel or not?}
\end{align}
$$
Question: given $K(x,z)$; how to understand if it is a kernel?
![[Merser's Theorem#Check Theorem]]

![[Merser's Theorem#Construction Theorem]]

## Polynomial Kernels
$$
\begin{align}
p(v) - \text{polynomial with non-negative coefs.} \\
\text{then  }K(x,z)= p(\left< x,z \right> ) - kernel \\
= \alpha_{n}\left< x,z \right> ^{n} + \dots + \alpha_{1}\left< x,z \right>  + \alpha_{0} \text{ -} \\
\text{- can be proven that it is a kernel by Merser's theorem}
\end{align}
$$
$$
\begin{align}
K(x,z) =\left( \left< x,z \right> +R \right) ^{m} - \text{ polynomial kernel } R>0, m \, \in \, \mathbb{N}  \\
= \sum_{i=0}^{m}C_{m}^{i}R^{m-1} \left< x,z \right> ^{i} 
\end{align}
$$
R - [[Regularization in ML]] for [[Monomial|monomials]] of big degrees. For regularization take $R \gg 0$


## Gaussian Kernels
$$
\begin{align}
K(x,z) = \exp \left( -\frac{{\lvert\lvert x-z \rvert\rvert ^{2}}}{2\sigma^{2}} \right) 
\end{align}
$$
apparently, $H$ - infinitely dimensional. but we can not even touch this dimensions. 

## [[K Nearest Neighbors (KNN)]]
Kernel methods have smoothly decreasing weights from 1 to 0 with some radius going from target point. In contrary [[K Nearest Neighbors (KNN)]] have 0/1 weights.
### Radial Basis Function (RBF)
(NN of infinite width (# of layers))
Correlations tends to 0. 


## Kernel Approximation
Use kernels => Need [[Gramm Matrix]] $K_{\ell \times \ell}$ => Probably we will not have enough memory. 

Idea: $\phi(x)$ - don't know, even if know, too big to store on GPU... Then let us find 
$$
\tilde{\phi}: \mathbb{X}\to \tilde{H} \quad s.t. \quad  \left< \tilde{\phi}(x), \tilde{\phi}(x) \right> \approx K(x,z) \quad \forall x,z 
$$
That will be our low-rank approximation of a [[Kernel Methods#Gaussian Kernels|Gaussian Kernel]]. 

### Random Fourier Features (Random Kitchen Sinks, RKS)
We will be working only with kernels of form:
$$
K'(x,z)= K(x-z) \quad \quad \quad \text{Functions that depend on } x-z 
$$
![[Boxner Theorem]]

$$
\begin{align}
\underbrace{ K(x-z) }_{ \text{real function} } = \int _{\mathbb{R}^{d}}p(w)e^{iw^{T}(x-z)} \, dw =  \\
= \int _{\mathbb{R}^{d}}p(w)\cos w^{T}(x-z)dw \, + \cancelto{ 0 }{ i\int_{\mathbb{R}^{d}}p(w)\sin w^{T}(x-z)dw C } = \\
 =\int _{\mathbb{R}^{d}} p(w)\cos w^{T}(x-z)\, dw = \{ w_{1},\dots w_{n}\sim p(w) \} \approx \\
\approx \frac{1}{n}\sum_{i=1}^{n}\cos w_{j}^{T}(x-z) = \dots
\end{align}
$$
Сильнее всего будут влиять те $\cos w^{T}(x-z)$, у которых большая вероятность $p(w)$ ([[Monte Carlo]] Approximation)

$$
\begin{align}
\dots = \frac{1}{n}\sum_{j=1}^{n}\left( \cos(w_{j}^{T}x)\cos(w_{j}^{T}z) + \sin (w_{j}^{T}x)\sin(w_{j}^{T}t) \right)  \\
\tilde{\phi}(x) = \frac{1}{\sqrt{ n }}\Big(\cos(w_{1}^{T}x), \dots \cos(w_{n}^{T}x), \sin(w_{1}^{T}x), \dots, \sin(w_{n}^{T}x)\Big) =  \\
= \left< \tilde{\phi}(x), \tilde{\phi}(z) \right> 
\end{align}
$$
So we got an approximation of a kernel with exact cos functions. 
$$
K(x,z) = \exp\Big(-\frac{{\lvert\lvert x-z \rvert\rvert^{2} }}{2\sigma^{2}}\Big) <=> p(w) = \mathcal{N}(0,\sigma^{2})
$$
X - training set
$$
\tilde{X} = \underbrace{ \begin{bmatrix}
\tilde{\phi}(x) \\
\dots \\
\tilde{\phi}(x)
\end{bmatrix} }_{ \begin{align}
\text{new features } \\
\text{approximating } \phi(x) \\
\text{from } K(x,z) 
\end{align} } \implies \text{Train Linear model } \left< w,\tilde{\phi}(x) \right> \text{ as usual}
$$


## Related:
[[SVM (Support Vector Machine)##Kernel Svm]]
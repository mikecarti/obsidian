[Sokolov's Lecture](https://github.com/esokolov/ml-course-hse/blob/master/2020-fall/lecture-notes/lecture05-linclass.pdf)

Maximizing the distance from hyperplane to points.
$$
\begin{align}
\tilde{L}(M)=max(0,1-M)
\end{align}
$$

### Constrained Optimization Goal
$$
\begin{cases}
\xi \geq 0  \\
\frac{1}{2} \lvert\lvert w \rvert\rvert^{2} + C\sum\xi_{i} \to \min_{{w,b,\xi}}  \\
y_{i} \cdot (\left< w,x_{i} \right> ) \geq 1 - \xi_{i}
\end{cases}
$$
(Make margin $\frac{1}{\lvert\lvert w \rvert\rvert^{2}}$ the biggest, while trying to classify maximal objects correctly)

### Unconstrained Optimization Goal
$$
\frac{1}{2}\lvert\lvert w \rvert\rvert ^{2} + C\sum_{i=1}^{l} \xi_{i} = \frac{1}{2}\lvert\lvert w \rvert\rvert ^{2} + C\sum_{i=1}^{l} \max_{}(0, y \cdot (\left< w,x_{i} \right> + b )) \quad \to \min_{w,b}
$$
## How to select best hyperplane?
![[Pasted image 20231103112337.png]]

Red makes minimal amount of assumptions.

## Linearly Separable Case
$$
\begin{align}
&\exists w \text{ s.t. } y:   \\
&y= sign(\langle \alpha w, x \rangle + \alpha w_{0}) \text{ - we try to achieve that, because sign shows } \\
&\text{from which side of hyperplane the data lies} \\
&\min_{x_{i}\in X} \lvert \langle w,x_{i} \rangle + w_{0} \rvert = 1 \text{ - can be achieved with scaling of parameters} 
\end{align}
$$


### Distance from point x to a line $\alpha$ with normal vector w:
$$
\begin{align}
&\rho(\alpha ,x)= \frac{{\mid \langle w,x \rangle +w_{0} \mid}}{\lvert \lvert w \rvert  \rvert } \\
&\min_{x_{i}\in X}\rho(\alpha,x_{i})= \frac{\min_{x_{i}\in X}{\lvert \langle w,x \rangle + w_{0}  \rvert }}{\lvert \lvert w \rvert  \rvert }=  \\
& \frac{1}{\lvert \lvert w \rvert  \rvert } \min_{x_{i}\in X}{\lvert \langle w,x \rangle + w_{0}  \rvert } = \frac{1}{\lvert \lvert w \rvert  \rvert }  \\
\end{align}
$$
So nearest object is distanced by $\frac{1}{\lvert\lvert w \rvert\rvert}$ away from hyperplane $\left< w,x \right>$. That is our [[Margin]]. Thus width of it's splitting hyperplane is $\frac{2}{\lvert\lvert w \rvert\rvert}$


Then we can formalize our optimization problem as
$$
\begin{align}
&\begin{cases}
\frac{1}{\lvert \lvert w \rvert  \rvert }\to \max_{w} \\
y_{i}(\left< w,x_{i} \right> +w_{0})> 0  & i = 1,\dots,l \\
\min_{x_{i}\in X} \mid \left< w,x_{i} \right> + w_{0}  \mid = 1
\end{cases} \equiv \\ \\ \\

&\text{SVM opt. goal for separable case:} \\

& \equiv\begin{cases}
\lvert \lvert w \rvert  \rvert ^{2} \to \min_{w,w_{0}} \\
y_{i}  \cdot (\left< w,x_{i} \right> + w_{0}) \geq 1 & i = 1,\dots ,l
\end{cases}
\end{align}
$$

$w_{0}$ - bias term
Square in $\lvert\lvert w \rvert\rvert^{2}$ is for differentiability. And represents margin width maximization problem. $y_{i}  \cdot \left< w,x_{i} + w_{0} \right> \geq 1$ for every correctly separated object.


## Not linearly separable case
$$
\begin{align} &(**)\\
&\text{SVM opt. goal for unseparable case:} \\

&\forall w, w_{0} \quad \exists x_{i} \in X : y_{i}(\left< w,x_{i} \right> + w_{0})<0 \\
&\frac{1}{2}\lvert \lvert w \rvert  \rvert ^{2} + C\sum_{i=1}^{l}\xi_{i} \to \min_{w,w_{0}, \xi_{i}}  \\
&y_{i}(\left<  w,x_{i}+ w_{0}\right> ) \geq 1 - \xi_{i} \\
&\xi _{i} \geq 0
\end{align}
$$

$\lvert \lvert w \rvert \rvert^{2}$ - penalty for small distance to nearest object
$\sum_{i=1}^{n}\xi_{i}$ - penalty for mistakes of a model
$C$ - [[Hyperparameters|hyperparameter]]

![[Pasted image 20231103115353.png|200x200]]

### Unconditional Optimization Goal (\*\*)
$$
\begin{align}
&\begin{cases}
\xi _{i}\geq 1- y_{i}(\left< w,x_{i}+w_0 \right> ) \\
\xi_{i}\geq 0
\end{cases} = > \\
&\xi_{i} = max(0, 1 - y_{i}(\left< w,x_{i} \right>+ w_{0} )) \\
&\underbrace{ \frac{1}{2}\lvert \lvert w \rvert  \rvert ^{2} }_{ \mathrm{Re}gularization } + \underbrace{ C \sum_{i=1}^{l}\underbrace{ \max(0, 1 - y_{i}(\left< w,x_{i} \right> + w_0)) }_{ L(y,z)= max(0,1-yz) } }_{ Loss \quad Function } \to \min_{w, w_0}
\end{align}
$$

## Support Vectors
опорные векторы — это точки, которые а) расположены в точности на границах, б) внутри гиперплоскости, в) которые попали на сторону противоположного класса при классификации

### SVM estimates class probabilities badly..
To solve it there are methods like [[Platta Calibration]] and [[Isotonic Regression]].

## Difference between [[Linear Classification]] and SVM

![[Pasted image 20231103120806.png]]

given $M <0$ behavior is identical
given $M > 0$: 
	for SVM its enough to $M \geq 1$
	for LR, it is better when $M\to +\infty$

SVM gives better classification [[Metrics and Loss Functions|metrics]] values. (AUC-ROC, F-Score)

[[Linear Classification]] tends to correctly estimate probabilities

## Kernel SVM
It turns out, that if we write [[Dual Function]] of [[SVM (Support Vector Machine)#Constrained Optimization Goal|Constrained Optimization Goal in SVM]], we get a nice form for [[Kernel Methods|kernels]]. Lets write out the [[Lagrangian]]

$$
\begin{align}
&L(w,b,\xi,\lambda,\mu )=\frac{1}{2}\lvert\lvert w \rvert\rvert ^{2}+C\sum\xi_{i} -\sum_{i=1}^{l}\lambda_{i}(y_{i}(\left< w,x_{i} \right> +b)-1+\xi_{i}) - \sum_{i=1}^{l}\mu_{i}\xi_{i}  \\
&\nabla_{w}L=w -\sum_{i=1}^{l}\lambda_{i}y_{i}x_{i} = 0 \implies w=\sum_{i=1}^{l}\lambda_{i}y_{i}x_{i} \quad \quad (1) \\
&\nabla_{b}L=-\sum_{i=1}^{l}\lambda_{i}y_{i}=0 \\
&\nabla_{\xi_{i}}L=C-\lambda_{i}-\mu_{i}=0\implies\lambda_{i}+\mu_{i}=C
\end{align}
$$

By [[Complementary Slackness Theorem (KKT)]]
$$
\begin{align}

\lambda_{i}(y_{i}(\left< w,x_{i} \right> +b)-1+\xi_{i})=0 &\implies \begin{cases}
\lambda_{i}=0  \\
y_{i}(\left< w,x_{i} \right> +b) = 1- \xi_{i}  
\end{cases} \\
\mu_{i}\xi_{i}=0 \quad  &\implies \begin{cases}
\mu_{i}=0 \\
\xi_{i}=0 \\
\end{cases} \\
\lambda_{i}\geq 0, \mu_{i}\geq &0
\end{align}
$$

1) $\xi_{i}=0$, $\lambda_{i}=0$    -    peripheral objects (can be kicked out from training sample, and nothing will change)
	 $\lambda$ = 0 means that it does not influence weights.
	 ![[Pasted image 20240126151817.png]]
1) $\xi_{i}=0$,   $0< \lambda_{i}\leq C$   (- опорные граничные)
	$\lambda_{i}\neq 0$=> $y_{i}(\left< w,x_{i} \right>+ b)=1$
	![[Pasted image 20240126151759.png]]

3) $\xi_{i}=0$ => $\mu_{i}\geq 0$  => $\lambda_{i}=C$ (- опорные нарушители)![[Pasted image 20240126151747.png]]
---------

Substitute (1) in Lagrangian:
$$
\begin{align}
L = \frac{1}{2}\left\lvert \left\lvert  \sum_{i=1}^{l}\lambda_{i}y_{i}x_{i}   \right\rvert \right\rvert^{2} - \sum_{i=1}^{l}\sum_{j=1}^{l}\lambda_{i}\lambda_{j}y_{i}y_{j}\left<  x_{i}x_{j}  \right> -  \\
- \cancelto{ 0 }{ b\sum_{i=1}^{l}\lambda_{i}y_{i} }+\sum_{i=1}^{n}\lambda_{i}K+\cancelto{ 0 }{ \sum_{i=1}^{n}\xi_{i}(C-\lambda_{i}-\mu_{i}) }
\end{align}
$$
No direct variables (прямых) => It is [[Lagrangian#Dual Function|Dual Function]]:

### Dual Task for SVM
$$
\begin{cases}
\sum_{i=1}^{l}\lambda_{i} - \frac{1}{2}\sum_{i=1}^{l}\sum_{i=j}^{l}\lambda_{i}\lambda _{j}y_{i}y_{j}\left< x_{i},x_{j} \right> \to \max_{\lambda_{i}} \\
\sum_{i=1}^{l}\lambda_{i}y_{i}=0 \\
0 \leq \lambda_{i} \leq C  \\
\mu_{i}= C-\lambda_{i}
\end{cases}

$$

If we find solutions $\lambda_{i}^{*}$ then
$$w_{*}= \sum_{i=1}^{l}\lambda_{i}y_{i}x_{i}$$
So we get a form, where features are not needed (needed only [[Dot (Scalar) Product]])

### Kernel Trick (Final Form of Kernel SVM Optimization)
$$
\begin{align}
&\left< x_{i},x_{j} \right> \to K(x_{i},x_{j} ) = \left< \phi(x_{i}), \phi(x_{j}) \right>  \\
&\sum_{i=1}^{l}\lambda_{i} -\frac{1}{2}\sum_{i,j=1}^{l} \lambda_{i}\lambda_{j}y_{i}y_{j}K(x_{i},x_{j}) \to \max_{\lambda_{i}} \\
&\sum\lambda_{i}y_{i}=0 \\
&0 \leq \lambda_{i}\leq C
\end{align}
$$

We are building a model in the space where $\phi(x)$ gets us. 

### Problems
- Have to store [[Gramm Matrix]] (O(n^2) )
- Constrained Optimization
- Double sum of objects

### Model Structure
$$
\begin{align}
a(x) = sign(\left< w,x \right> +b)=  \\
=sign\left( \sum_{i=1}^{l}y_{i}\lambda_{i}\left< x_{i},x \right> +b \right) =  \\
= sign\left( \sum_{i=1}^{l}\lambda_{i}y_{i}K(x_{i}, x) + b \right)
\end{align} 
$$
#### How to find $b$?
Take $x_{i}$:  $\xi_{i}=0, \lambda_{i}>0$  (опорный граничный)
$$
y_{i}(\left< w,x_{i} \right>+b)=1
$$
$$
b=y_{i}-\left< w,x_{i} \right> =y_{i}-\sum0_{j=1}^{l}\lambda_{j}y_{j}\left< x_{i},x_{j} \right> 
$$

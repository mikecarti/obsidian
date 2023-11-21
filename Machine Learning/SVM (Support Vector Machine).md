$$
\begin{align}
\tilde{L}(M)=max(0,1-M)
\end{align}
$$

## How to select best hyperplane?
![[Pasted image 20231103112337.png]]

Red makes minimal amount of assumptions.

## Linearly Separable Case
$$
\begin{align}
&\exists w \text{ s.t. } y:   \\
&y= sign(\langle \alpha w, x \rangle + \alpha w_{0}) \\
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
y_{i}(\left< w,x_{i} \right> + w_{0}) \geq 1 & i = 1,\dots ,l
\end{cases}
\end{align}
$$
$w_{0}$ - bias term


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


![[Pasted image 20231103115353.png]]

### Simplifying Optimization Goal (\*\*)
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

## Difference between [[Linear Classification]] and SVM

![[Pasted image 20231103120806.png]]

given $M <0$ behavior is identical
given $M > 0$: 
	for SVM its enough to $M \geq 1$
	for LR, it is better when $M\to +\infty$

SVM gives better classification [[Metrics and Loss Functions|metrics]] values. (AUC-ROC, F-Score)

[[Linear Classification]] tends to correctly estimate probabilities
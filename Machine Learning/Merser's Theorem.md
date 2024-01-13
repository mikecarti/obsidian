## Check Theorem
Function $K(x,z)$ is a kernel IFF:
1) $K(x,z)= K(z,x)$
2) $K(x,z)$ is semi-positive definite (неотрицательно определена)
	$\forall l \quad  \forall(x_{1},\dots x_{l})\subset \mathbb{X}$
	$K = (K(x_{i}, x_{j}))^{l}_{i,j=1}$

Hard to check (2), instead rule for [[Kernel Methods|Kernel]] construction can be made.

## Construction Theorem 
$$
\begin{align}
K_{1}(x,z), K_{2}(x,z)- kernels \\
f: \mathbb{X}\to \mathbb{R} \\
\mu: \mathbb{X}\to \mathbb{R}^{N} \\
K_{3}: \mathbb{R}^{n}\times \mathbb{R}^{n}\to R \text{ - kernel}
\end{align}
$$
Then these all are *kernels*: 
1) $K(x,z)=K_{1}(x,z)+ K_{2}(x,z)$
2) $\alpha K_{1}(x,z), \alpha>0$
3) $K_{1}(x,z)K_{2}(x,z)$ 
4) $K(x,z)= f(x)f(z)$ 
5) $K_{3}(\mu(x),\mu(z))$ 

## Theorem
given sequence $K_{1}(x,z), \dots K_{n}(x,z),\dots$ - kernels
$$
\begin{align} \\
\exists \lim_{ n \to \infty } K_{n}(x,z) \quad  \forall x,z \\
\implies K(x,z)= \lim_{ n \to \infty } K_{n}(x,z) - \text{kernel} 
\end{align}
$$

$$
\begin{align}
\begin{cases}
\frac{1}{2} \lvert\lvert w \rvert\rvert ^{2} + \frac{1}{lV}\sum_{i=1}^{l}\zeta_{i} - \rho \to \min_{w,\zeta,\rho} \\
\left< w,x_{i} \right> \geq \rho - \zeta_{i} \\
\zeta_{i} \geq 0 
\end{cases}
\end{align}
$$
#### Informally this definition puts these requirements:
1) Get a hyperplane $\left< w,x \right>= \rho$
2) Most objects would be from one side
3) Try to make hyper-plane as further from zero as possible

Therefore we are calculating 0 anomalies and separate sample from these anomalies with maximum step.

To make everything logical, let us build a [[Dual Function]] and make a [[Kernel Methods|Kernel transition]] 

$$
\begin{align} \\
\begin{cases}

&\frac{1}{2}\sum_{i,j=1}^{l}\lambda_{i}\pi_{j}K(x_{i}, x_{j}) \to \min_{\lambda} \\
&0 \leq \lambda_{i} \leq \frac{1}{Vl} \\
&\sum_{i=1}^{l}\lambda_{i} = 1  \\
\end{cases}

\end{align}
$$

$$
\begin{align}
a(x) = sign\left( \sum_{i,j=1}^{l}\lambda_{i}K(x_{i}, x_{j})  - \rho \right) \text{ - model} \\
K(x,z) = \exp\left( -\frac{{\lvert\lvert x-z \rvert\rvert  }}{2\sigma^{2}} \right) \\
a(x) = sign\left( \sum_{i=1}^{l}\lambda_{i}y_{i}\exp\left( -\frac{{\lvert\lvert x-x_{i} \rvert\rvert}}{2\sigma^{2}}\right) -\rho  \right)
\end{align}
$$
If object is afar from all objects X, then $a(x)=-1$
Find $\lambda_{1}, \dots, \lambda_{l}$ so that only X area had $a(x)=+1$
Find area of minimal object that has the full sample.


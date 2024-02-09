![[Pasted image 20240204205854.png]]
a)
$$
\begin{align}
b_{t} = t^{2} + 6t + u_{t} - 4Lu_{t} - 4L^{2}u_{t} \implies   \\
b_{t} = t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2}
\end{align}
$$
b) 
$$
\begin{align}
E(b_{t}) = E\left[ t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2} \right] = \\
= E\left[ t^{2} \right] + 6E[t] - \cancelto{ 0, \text{White Noise} }{ 4E[u_{t-1}] } + \cancelto{ 0 }{ E[u_{t}] } - \cancelto{ 0 }{ 4E[u_{t-2}] }  
= t^{2} + 6t  \\ \\
Var(b_{t}) = Var\left[ t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2} \right] =  \\
= Var\left[u_{t} - 4u_{t-1} - 4u_{t-2} \right] = \{ Cov(u_t,u_{s})=0 \} = \\
= Var[u_{t}] + 16Var[u_{t-1}] + 16Var[u_{t-2}] = 33\sigma^{2}
\end{align}

$$
с) 
$$
\begin{align}
&Cov(b_{t}, b_{t-k}) = Cov\Big(t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2}; \quad  (t-k)^{2} + 6(t-k) + u_{(t-k)} - 4u_{t-k-1} - 4u_{t-k-2}\Big)= \\
&1)\; k=0 \\
& \quad Cov(b_{t},b_{t}) = 33\sigma^{2} \\
&2)k=\pm1 \\
& \quad  Cov(b_{t},b_{t-1}) = Cov(t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2};\; (t-1)^{2} + 6(t-1) + u_{(t-1)} - 4u_{t-2} - 4u_{t-3} )= \\
&=Cov(-4u_{t-1}; \;u_{t-1}) + Cov(-4u_{t-2};\;4u_{t-2}) = -4\sigma -16\sigma =-20\sigma^{2}  \\
&3) k =\pm2 \\
& \quad  Cov(b_{t}, b_{t-2}) = Cov(t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2};\; (t-2)^{2} + 6(t-2) + u_{(t-2)} - 4u_{t-3} - 4u_{t-4} )= \\
&=Cov(-4u_{t-2}; \; u_{t-2}) = -4\sigma^{2} \\
&4) k \geq 3 \cup k\leq-3 \\
& \quad Cov(b_{t, b_{t-k}}) = 0
\end{align} 
$$
$$
\begin{align}
Corr(b_{t}, b_{t-k}) 
=\begin{cases}
1  & k=0 \\
-\frac{20}{ 33 }  & k=\pm1 \\
-\frac{4}{\sqrt{ 33 }} & k=\pm2 \\ 
0  & k\geq 3 \cup k\leq-3
\end{cases}
\end{align}
$$
d) E is constant, Var is constant, Auto-Covariance does not depend on time. Thus it is one of [[Weakly Stationary Processes]]


![[Pasted image 20240208233428.png]]
a) $E(y_{t}), Var(y_{t})$
$$
\begin{align}
E(y_{t}) = E[1] + E[u_{t}] + 0.7E[u_{t-1}] + \dots = 1 \\ \\
Var(y_{t}) = Var(1 + u_{t} + 0.7u_{t-1} + 0.7^{2}u_{t-2} + \dots) = \\
= V(1) + V(u_{t}) + 0.7^{2}V(u_{t-1}) + 0.7^{4}V(u_{t-2}) + \dots = \\
=\sigma^{2} (1 + 0.7^{2} + 0.7^{4} + 0.7^{6} + \dots) =  \\
= \lim_{ n \to \infty }  \sigma^{2} \left( \frac{{1(1-0.7^{2n})}}{1-0.7^{2}} \right) = \sigma^{2} \frac{1}{1-0.49} = \sigma^{2} \frac{1}{0.51} = \frac{100\sigma^{2}}{51}
\end{align}
$$

b) $Cov(y_{t}, y_{t-k})$
$$
\begin{align}
Cov(y_{t}, y_{t-k}) \\
k = 0\implies Cov(y_{t}, y_{t-k})= Var(y_{t})  = \frac{100\sigma^{2}}{51} \\
k = \pm 1 \implies Cov(y_{t}, y_{t-1}) = Cov (1 + u_{t} + 0.7u_{t-1}\dots; \; 1 + u_{t-1} + 0.7u_{t-2} + \dots) =  \\
= Cov(0.7u_{t-1}, u_{t-1}) + Cov(0.7^{2}u_{t-2} , 0.7u_{t-2}) + \dots =  \\
=  0.7Cov(u_{t-1}, u_{t-1}) + 0.7^{3}Cov(u_{t-2} , u_{t-2}) + \dots \\
k = \pm 2 \implies Cov(y_{t}, y_{t-2}) = Cov (1 + u_{t} + 0.7u_{t-1}\dots; \; 1 + u_{t-2} + 0.7u_{t-3} + \dots) =   \\
0.7^{2}Cov(u_{t-2}, u_{t-2}) + 0.7^{4}Cov(u_{t-3}; u_{t-3}) + \dots \\
k=\pm3 \implies Cov(y_{t}, y_{t-3}) = Cov (1 + u_{t} + 0.7u_{t-1}\dots; \; 1 + u_{t-3} + 0.7u_{t-4} + \dots) = \\
= 0.7^{3}Cov(u_{t-3}; u_{t-3}) + 0.7^{5} Cov(u_{t-4}; u_{t-4}) + \dots= \sum_{i=k-1}^{n} 0.7^{(2i+1 )} \\
Cov(y_{t};y_{t-k}) = \begin{cases}
\frac{100\sigma^{2}}{51} & k=0 \\
\sum_{i=k-1}^{n} 0.7^{(2i+1 )} & k\neq 0
\end{cases} \\
\lim_{ n \to \infty } \sum_{i=k-1}^{n} 0.7^{(2i+1 )} 
\end{align}
$$
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
&2)k=1 \\
& \quad  Cov(b_{t},b_{t-1}) = Cov(t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2};\; (t-1)^{2} + 6(t-1) + u_{(t-1)} - 4u_{t-2} - 4u_{t-3} )= \\
&=Cov(-4u_{t-1}; \;u_{t-1}) + Cov(-4u_{t-2};\;4u_{t-2}) = -4\sigma -16\sigma =-20\sigma^{2}  \\
&3) k =2 \\
& \quad  Cov(b_{t}, b_{t-2}) = Cov(t^{2} + 6t + u_{t} - 4u_{t-1} - 4u_{t-2};\; (t-2)^{2} + 6(t-2) + u_{(t-2)} - 4u_{t-3} - 4u_{t-4} )= \\
&=Cov(-4u_{t-2}; \; u_{t-2}) = -4\sigma^{2} \\
&4) k \geq 3 \\
& \quad Cov(b_{t, b_{t-k}}) = 0
\end{align} 
$$
$$
\begin{align}
Corr(b_{t}, b_{t-k}) 
=\begin{cases}
1  & k=0 \\
-\frac{20}{\sqrt{ 33 }}  & k=1 \\
-\frac{4}{\sqrt{ 33 }} & k=2 \\ 
0  & k\geq 3
\end{cases}
\end{align}
$$


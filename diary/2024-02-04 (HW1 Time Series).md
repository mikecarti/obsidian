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
c) E is constant, Var is constant, Cov($y_{t}, y_{t-k})$ does not depend on t, only on k. => It is weakly stationary.
d) Brah you kiddin? Im on latex how am gona drow dat xDDDD


![[Pasted image 20240209162331.png]]
![[Weakly Stationary Processes#Definition]]

$$
\begin{align}
a_{t} = \cos t + u_{t} \\
b_{t} = \sin t +  u_{t}  \\
 \\
s_{t} = \cos{t} + \sin{t} + 2u_{t} \\
cov(s_{t}, s_{t+s})=  \\
=Cov(\cos{t} + \sin{t} + 2u_{t}; \; \cos{(t+s}) + \sin{(t+s)} + 2u_{t+s})   \\
\text{As sum of periodic functions is not periodic, thus cov is dependent on t}
\end{align}
$$


![[Pasted image 20240209211543.png]]

$$
\begin{align}
Cov(y_{1},y_{2}) = 0 \implies Corr(y_{1},y_{2}) = 0
\end{align}
$$
$$
\begin{align}
pCorr(y_{1},y_{2};y_{3}) 
\end{align}
$$
![[(PACF) Partially Correlated Function]]

$y_{1}^{*}= y_{1} - \alpha y_{3}$       s.t. $Cov(y_{1}^{*}, y_{3})=0$
$$
\begin{align}
Cov(y_{1}^{}-\alpha y_{3}, y_{3}) =0 \\
Cov(y_{1}, y_{3}) - \alpha Cov(y_{3},y_{3}) =0 \\
\alpha = \frac{Cov(y_{1},y_{3})}{Var(y_{3})} = -\frac{1}{4} \\
y_{1}^{*} = y_{1} +\frac{1}{4}y_{3} \\
  \\
Cov(y_{2}^{}-\alpha y_{3}, y_{3}) =0 \\
Cov(y_{2}, y_{3}) - \alpha Cov(y_{3},y_{3}) =0 \\
\alpha = \frac{Cov(y_{2},y_{3})}{Var(y_{3})} = \frac{1}{4} \\
y_{2}^{*} = y_{2} -\frac{1}{4}y_{3} \\
\end{align}
$$
$$
\begin{align}
Corr\left( y_{1}+\frac{1}{4}y_{3};\;y_{2}-\frac{1}{4}y_{3} \right) = \\
= \frac{{Cov\left( y_{1}+\frac{1}{4}y_{3} ; \; y_{2}-\frac{1}{4}y_{3}\right)}}{\sqrt{ Var\left(  y_{1}+\frac{1}{4}y_{3}  \right) }\sqrt{ Var\left(  y_{2}-\frac{1}{4}y_{3} \right)  }} \\
 Var\left(  y_{1}+\frac{1}{4}y_{3}  \right) = Var(y_{1}) + Var\left( \frac{1}{4}y_{3} \right) + 2Cov\left( y_{1}, \frac{1}{4}y_{3} \right)  \\
 Var\left(  y_{1}+\frac{1}{4}y_{3}  \right) = Var(y_{1}) + \frac{1}{16}Var\left( y_{3} \right) + \frac{1}{2}Cov\left( y_{1}, y_{3} \right) =  \\
= 16 + \frac{1}{4} -\frac{1}{2} =15.75 \\ \\
 Var\left(  y_{2}-\frac{1}{4}y_{3} \right) =Var(y_{2}) + \frac{1}{16}Var\left( y_{3} \right) - \frac{1}{8}Cov\left( y_{2}, y_{3} \right)=   \\
=4 + \frac{1}{4} -\frac{1}{8} = 4.125 \\ \\
\end{align}
$$
$$
\begin{align}
&Cov\left( y_{1}+\frac{1}{4}y_{3};\;y_{2}-\frac{1}{4}y_{3} \right) = \frac{1}{8} Cov(4y_{1} + y_{3}; \; 4y_{2} -y_{3})= \\
&= \frac{1}{8}(Cov(4y_{1},4y_{2}) + Cov(4y_{1}, -y_{3}) + Cov(y_{3}, 4y_{2})+ Cov(y_{3}, -y_{3})) = \\
&=\frac{1}{8}\left( 0 + 4 + 4 -4 \right) = \frac{1}{2}  \\
&pCorr = Corr\left( y_{1}+\frac{1}{4}y_{3};\;y_{2}-\frac{1}{4}y_{3} \right) \approx \frac{1}{2} / \left( 2,03  \cdot  3,96\right) \approx 0.622
\end{align}
$$

![[Pasted image 20240209225002.png]]

$$
\begin{align}
y_{t} = 5+u_{t}+u_{t-1}+u_{t-2}
\end{align}
$$
a)
$$
\begin{align}
&E(y_{t}) = 5+ 0 + 0 + 0= 5 \\
&Var(y_{t}) = Var(5+u_{t}+u_{t-1}+u_{t-2}) = 3\sigma^{2} \\
&Cov(y_{t}, y_{t+0}) = \sigma^{2} \\
&Cov(y_{t}, y_{t-1}) = Cov(5+u_{t}+u_{t-1}+u_{t-2};\; 5+u_{t-1}+u_{t-2}+u_{t-3})= \\
&=2\sigma^{2} \\
&Cov(y_{t}, y_{t-2}) = \sigma^{2} \\
&k \geq 3 \quad Cov(y_{t}, y_{t-k}) = 0 \\
\implies &\text{Weakly Stationary} \\
&\gamma(s) = \begin{cases}
\sigma^{2} & s=0 \\
2\sigma^{2} & s=1 \\
\sigma^{2} & s = 2 \\
0 & s \geq 3
\end{cases}
\end{align}
$$

b) ![[Auto-Correlation Function (ACF)]]
$$
\begin{align}
\rho(s) = \begin{cases}
1 & s = 0 \\
2 & s = 1 \\
1 & s = 2  \\
0 & s \geq 3
\end{cases}
\end{align}
$$

c)
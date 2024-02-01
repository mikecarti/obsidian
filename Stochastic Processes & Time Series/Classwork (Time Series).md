## 18.01 Seminar
$$
y_{t} = u_{t} + b_{1}u_{t-1} \quad \quad \quad \text{ ->Moving average.   Stationary?}
$$
1) $E(yt) = Eu_{t} + b_{1}Eu_{t-1}=0$
2) $Var(y_t)= var(u_t) + b_{1}^{2}var(u_{t-1}) =(1+\beta_{1}^{2})\sigma^{2}$
3) $Cov(y_{t},y_{t+s})$ - ?
$s = 0$         $\gamma(0)\equiv var(y_{t})$
$s = 1$         $\gamma(1) \equiv cov(y_{t},y_{t+1}) = \beta_{1}\sigma^{2}$
$\gamma_{i}$ - [[Auto-Correlation Function]]

$\to$ MA1 is stationary

Task 2
$$
\begin{align}
y_{t} = 1 -u_{t} +0.1u_{t-1}+0.2u_{t-2} \quad \text{MA(2)}
\end{align}
$$
1) $Ey_{t} = 1$
2) $Var(y_{t}) = var(-u_{t})+var(0.1u_{t-1})+var(0.2u_{t-2})$
$= 1.05\sigma^{2}$
3) $cov(y_{t},y_{t+1})=cov(-u_{t}+0.1u_{t-1}+0.2u_{t-2}, -u_{t+1}$$+0,1u_{t}+0.2u_{t-1}) = -0.1\sigma^{2}+0.02\sigma^{2}=-0.08\sigma^{2}$ 
     $$
\begin{align}
cov(y_{t},y_{t+2}) = cov(\dots,   \; \dots) = -0.2u_{t}
\end{align}
$$

Task3
$$
\begin{align}
y_{t} = a_{1}y_{t-1}+ u_{t} \\ \\
\text{Each sequence of y is a solution} \\
1) E(y_{t}) = E(y_{t-2}+u_{t-1}+u_{t}) = E\left( y_{0}+\sum_{i=1}^{t}u_{i} \right) = y_{0} \\
2) var(y_{t}) = var\left( y_{0}+ \sum_{i=1}^{t}u_{i} \right) = tvar(u_{t}) \\
y_{t} \to \text{ is not stationary by definition} 
\end{align}
$$

How to check just by looking? 


## 01.02 Seminar
### Task 1
$$
y_{t}= 0.3y_{t-1} + u_{t}
$$
$$
\begin{gather*}
y_{t}- 0.3Ly_{t}= u_{t} \\
(1-0.3L)y_{t}= u_{t} \\
\lambda = 0.3 \implies \text{by theorem of infinite MA} \\
\mid \lambda\mid <1 \text{ -> MA infinite with 1 stationary } \\
\rho(s) = 0.3^{s}   \\
\^: y_{t} = 0.3y_{t-1} + u_{t} \equiv
\end{gather*}
$$
By [[Yule Walker equation]]: 
$$
\begin{gather*}
Corr(y_{t}, y_{t-1})= corr(0.3y_{t-1}+u_{t}, y_{t-1}) =  \\
= 0.3corr(y_{t-1}, y_{t-1})+ corr(u_{t}, y_{t-1}) \\
\rho(1) = 0.3  \cdot  \rho(0) + 0 = 0.3  \cdot  1 = 0.3 \implies \\
\rho(s) = 0.3^{s} \\ \\
corr(y_{t}, y_{t-5}) = 0.3^{5} \text{<- effect of changes in y(t-5) on y(t)} \\
\text{But what is the direct effect of } y_{t-5} \text{ on  } y_{t}?  \\
y_{t} = \phi_{51}y_{t-1} + \phi_{52}y_{t-2} + \phi_{53}y_{t-3} + \phi_{54}y_{t-4} + \phi_{55}y_{t-5} + \epsilon_{t} \\
\phi_{5i} \text{ - effect of } y_{t-5} \text{ on a variable} \\
\text{Then } \phi_{55} \text{ is the direct effect!}
\end{gather*}
$$

pacf - [[Partial Autocorrelation Function]]
$$
pacf(s)= \phi(s) = pcorr(y_{t}, y_{t-s};y_{t-s}, y_{t-2},  \dots,y_{t-s+1})
$$

$$
\begin{align}
y_{t} = 0.3y_{t-1} + u_{t} \\
1) \quad prcorr(y_{t},y_{t-1})\equiv \phi(1) \\
y_{t} = \phi_{11}y_{t-1} + \epsilon_{t} \quad \quad \text{What is } \phi_{11}? \\
\text{intuition:  } \phi_{11} = 0.3 \\
2) pcorr(y_{t}, y_{t-2};y_{t-1} ) \equiv \phi(2) \\
y_{t} = \phi_{21}y_{t-1} + \phi_{22}y_{t-2}+\epsilon_{t} \\
3) pcorr(y_{t}, y_{t-3}; y_{t-1}, y_{t-2}) \equiv \phi(3) = \phi_{33}  \\
y_{t} = \phi_{31}y_{t-1} + \phi_{32}y_{t-2}+ \phi_{33}y_{t-3} + \epsilon_{t} \\
\implies \text{PACF: } \phi(s)=0 \quad s>p \quad AR(p) \\ \\
\text{Formally: } \\
y_{t}=0.3y_{t-1}+u_{t} \text{ <- AR(1)   p=1} \\
1) \quad  \phi(1) = \phi_{11} \quad  \underbrace{ y_{t}=\phi_{11}y_{t-1}+ \epsilon_{t} }_{ \text{Estimate it!} } \\
\end{align}
$$
Using [[Yule Walker equation]]:
$$
\begin{align}
&\rho(1) = \underbrace{ \phi_{11} }_{ \text{unknown} }  \cdot \;\; 1 \implies \phi_{11} =\phi(1) = 0.3 \\
&2) \phi(2) = \phi_{22}  \\
&y_{t}= \underbrace{ \phi_{21}y_{t-1}+\phi_{22}y_{t-2}+\epsilon_{t} }_{ \text{2 unkonwn vars: }\phi_{21}, \phi_{22} } \\ \\
&\begin{cases}
\rho(1) = \phi_{21}  \cdot  1 + \phi_{22}\rho(1) & (Corr(y_{t-1}, y_{t}))\\
\rho(2) = \phi_{21} \cdot \rho(1)+ \phi_{22}  \cdot  1 & (Corr(y_{t-2}, y_{t}))
\end{cases} \\ \\

&\text{by Cramer's Rule solve system:} \\
&\Delta = \begin{vmatrix}
1 & \rho(1) \\
\rho(1)  & 1
\end{vmatrix} \\
&\Delta_{22} = \begin{vmatrix}
1 & \rho(1) \\
\rho(1) & \rho(2)
\end{vmatrix} \\
&\phi_{22} = 0 = \phi_{2}
\end{align}
$$
### Task 3
$$
\begin{align}
y_{t}= u_{t}+ 0.1u_{t-1}+0.2u_{t-2}
\end{align}
$$
- $y_{t}$ -> [[Weakly Stationary Processes]]
- $Ey_{t}, \dots, \rho(s)$
- $\phi(s)$ - ? 

What is PACF equal to?


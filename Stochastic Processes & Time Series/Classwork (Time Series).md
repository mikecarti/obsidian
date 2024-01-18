## 18.01
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
## Definition (Weak Stationarity)
1) $E(y_{t}) = \mu$
2) $Var(y_{t})=\sigma^{2}$
3) $cov(y_{t}, y_{t+s})= \gamma(s)$


## Check stationarity by viewing at a process.
$$
\begin{align}
y_{t}&= y_{t-1}+ u_{t} \\
y_{t-1} &=Ly_{t} \quad  y_{t-2}=L^{2}y_{t} \\
y_{t+1}&=L^{-1}y_{t}
\end{align}
$$
1) $y_{t}=Ly_{t}+u_{t} \to y_{t}-Ly_{t}=u_{t}$
$(1-L)y_{t}=u_{t}$
2) $(1-L)=\beta(L)$
3) find roots: $1-L = 0 \to L=1$
4) if polynomial equation has a root $\hat{L}$: 
$\mid L\mid = 1$ -> equation for $y_{t}$ doesn't have stationary solutions.
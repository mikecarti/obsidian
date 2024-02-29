
$$
\begin{matrix}
0  & +  & - \\
order & хз  & - \\
rank & + & хз
\end{matrix}
$$

# Example
N1
![[Pasted image 20240229144928.png]]
Solve system of equations
$$
\begin{cases}
c_{t} = \alpha_{1} + \alpha_{2} y_{t} + \alpha_{3}c_{t-1} + u_{1t} \\
i_{t} = b_{1} + b_{2}r_{t} + b_{3}y_{t} + u_{2t} \\
y_{t} = c_{t} + g_{t} + i_{t}
\end{cases}
$$

Exogenous: $r_{t}; g_{t}; c_{t-1}$ 

Order condition:
M - number of equations

excluded (собираем уравнения которых нет в этом уравнении, *omitted*)
1: $i_{t};r_{t}; g_{t}$ > (M-1) = 2  - works
2: $c_{t}; c_{t-1}; g_{t}$ > (M-1) = 2 - works
3: all coefficients are known for 3rd equation, so we don't need to check

Rank condition:
1: $$
\begin{align}
\begin{matrix}
i_{t} & r_{t} & g_{t} \\
-1  & \beta_{2}  & 0 \\
1  & 0  & 1
\end{matrix} \quad  rank =2 = M-1
\end{align}
$$
2: 
$$
\begin{align}
\begin{matrix}
c_{t} & c_{t-1} & g_{t} \\
-1 & \alpha_{3} & 0
\end{matrix} \quad  rank=2 = M-1
\end{align}
$$

b) use [[2 Step Least Squares (2SLS)]] 
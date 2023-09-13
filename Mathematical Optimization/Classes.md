[[Mathematical Optimization]]
# 12.09
№1
$$
4x_{1}+7x_{2}+6\to extr
$$
$$
\begin{equation}
    \begin{cases}
      2x_{1}-3x_{2} \leq 6\\
      x_{1}+x_{2} \leq 10  \\
	 2x_{1}-2x_{2}\geq 3 \\
2x_{1}-x_{2}\geq 0 \\
x_{1}\leq 6 \\
x_{1}\geq 0, x_{2}\geq 0
    \end{cases}\,.
\end{equation}
$$
$$
\text{Let } 4x_{1}+7x_{2}+6=6 
$$

$$
\left( \frac{f(x_{1})}{\nabla x_{1}}, \frac{f(x_{2})}{\nabla x_{2}}, \dots \right)
$$
$ax_{1}+bx_{2}+c \to n(a,b)$
gradient in this case is $(4,7)$

$x_{1} = \frac{-1}{4}(7x_{2} + a)$

![[Pasted image 20230912165700.png]]


№2
$$
L(x)=3x_{1}+2x_{2}-x_{3}+5x_{5}
$$
$$
\begin{cases}
x_{1}+2x_{2}-3x_{3}+11x_{4}+8x_{5}=-8 \\
-2x_{1}+x_{2}+x_{3}-7x_{4}+9x_{5}=6 \\
x_{1}+x_{2}+x_{3}+2x_{4}-6x_{5}=27 \\
x_{j} \geq 0;\;\; j = \bar{1,5}
\end{cases}
$$

n - variables
r - rank of equation system

$n-r=2$
$n -r \leq 2$

#### Gaussian elimination (RREF)
$$
\begin{align}

\begin{bmatrix}
1 & 2 & -3 & 11 & 8 & 8 \\
-2 & 1 & 1 & -7 & 9 & -6 \\
1 & 1 & 1 & 2 & -6 & -27 \\
3 & 2 & -1 & 0 & 5 & L
\end{bmatrix} \sim  \\ \\

\sim\begin{bmatrix}
1 & 0 & 0 & 3 & -5 & 7 \\
0 & 1 & 0 & 1 & 2 & 9\\
0 & 0 & 1 & -2 & -3 & 11\\
0 & 0 & 0 & -12 & 13 & L-28 \\
\end{bmatrix}
\end{align}
$$
$$
L(X) = -13x_{4}+13x_{5}+28
$$
$$
\begin{cases}
x_{1}=7-3x_{4}+5x_{5} \geq 0\\
x_{2}=9-x_{4}-2x_{5}\geq 0 \\
x_{3}=11+2x_{4}+3x_{5} \geq 0
\end{cases} \implies \begin{cases}
3x_{4}-5x_{5}\leq 7 \\
x_{4}+2x_{5}\leq 9 \\
2x_{4}+3x_{5} -11
\end{cases}
$$


$$
\begin{align}
max \; A(0;4.5)  \\
L(A)=86.5 \\
min  \; B\left( \frac{59}{11} =x_{4};\frac{20}{10} =x_{5}\right) \\
L(B) = -\frac{199}{11} \\
x_{1} \; min \\
x_{2} \;min \;\; max \\
x_{3} \; min \;\; max
\end{align}
$$
A, B - points on coordinate plane.
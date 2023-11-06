
![[Pasted image 20231105165318.png]]

№1
$$
\begin{align}
&df(x))/(dx) = ({2x3-6x-36})/(|2x3-6x-36|)  · (6x2 -6) = \\
&= 6(x^{2}-1) \frac{{(x^{3}-3x-18)}}{|x^{3}-3x-18 |} = 0 \\
&x = \{ 1, -1 \} - \text{ extremas} \\
&f(1) = \mid 2 - 6 - 36 \mid = 40 \\
&f(-1) = | -2 + 6 -36 | = 32   \\
&f(0) = -6 \\
&f(-100) < 0 \\
&f(100)  > 0 \\ \\
&x =1 - \text{ global minima}
\end{align}
$$

![[Drawing 2023-11-05 17.18.45.excalidraw]]

№3
$$
\begin{align}
&q(x) = 455*x_1^2 − 156*x_1*x_2 − 668*x1*x3 + 206*x1*x4 − 136*x1 + 672*x2^2 -  \\
&− 72*x2*x3 − 12*x2*x4 − 1224*x2 + 722*x3^2 + 524*x3*x4 +  \\
& +2312*x3 + 599*x4^2 + 3400*x4 
\end{align}

$$
$$
\begin{align}
&\nabla_{q} = \begin{bmatrix}
910x_{1} - 156x_{2}-668x_{3}+206x_{4}-136 \\
-156x_{1}+1344x_{2}-72x_{3}-12x_{4}-1224 \\
-668x_{1}-72x_{2}+1444x_{3}+524x_{4}+2312 \\
206x_{1}-12x_{2}+524x_{3}+1198x_{4}+3400
\end{bmatrix} = \begin{bmatrix}
0 \\
0 \\
0 \\
0
\end{bmatrix} \implies \\ \\

&\implies \text{stationary point: }   
\begin{bmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4} \\
\end{bmatrix} = \begin{bmatrix}
1 \\
1 \\
0 \\
-3
\end{bmatrix}\\ \\







&H_{q}=\begin{bmatrix}
910 & -156 & -668 & 206 \\
-156 & 1344 & -72 & -12 \\
-668 & -72 & 1444 & 524 \\
206 & -12 & 524 & 1198 \\
\end{bmatrix}  \\ \\

&\det(H_{q} - \lambda I) = \begin{vmatrix}
910 - \lambda & -156 & -668 & 206 \\
-156 & 1344 - \lambda & -72 & -12 \\
-668 & -72 & 1444 - \lambda & 524 \\
206 & -12 & 524 & 1198 - \lambda \\
\end{vmatrix}  = \\
&= λ^4 - 4896 λ^3 + 8115120 λ^2 - 5025881088 λ + 727394411520 = 0 \\

&\vec{\lambda} = \{ 204,1224,1428, 2040 \} > 0 \implies \vec{x} = \{ 1,1,0,-3 \} \text{ is a minimum point}  \\
\end{align}

$$

№2
```python
import numpy as np
from sympy import lambdify, parse_expr
from math import log

def get_new_interval_golden_ratio(a, b, func, fa_=None, fb_=None):
    golden_ratio = (3 - 5**0.5) / 2
    an = a + golden_ratio * (b - a)
    bn = b - golden_ratio * (b - a)
    print(f"New interval: [{an}, {bn}]")
    fa = fa_ if fa_ is not None else func(an)
    fb = fb_ if fb_ is not None else func(bn)
    
    if fa < fb:
        return a, bn, None, fa
    else:
        return an, b, fb, None

fstr = "x**4 - 25*x**3 + 215*x**2 - 680.5*x + 624"
f = lambdify(["x"], parse_expr(fstr))
a, b = [-0.5, 12]
tolerance = 0.01
golden_ratio = (3 - 5**0.5) / 2
N = int(np.ceil(log(tolerance / (b - a), (1 - golden_ratio))) )
print(f"Number of iterations: {N}")
fa, fb = None, None

for _ in range(N):
    a, b, fa, fb = get_new_interval_golden_ratio(a, b, f, fa_=fa, fb_=fb)

x = 2.591302703383936
y = 2.594803123159844
print((x+y)/2)
print(f((x+y)/2))
```
![[Pasted image 20231105184405.png|400]]

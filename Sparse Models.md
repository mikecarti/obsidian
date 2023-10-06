Why should we nullify some weights?
1) We throwed every possible feature in a model
2) Model Acceleration
3)  $N \ll p$ ; $\ell \ll d$.    $N$ - кол-во наблюдений, $\ell$ - кол-во признаков

## Solution for linear models:
[[Regularization#LASSO | L1 Regularization]]

$$
Q(w)+\lambda| | w| |_{1} \to \min_{w}
$$
#### Why does this work?
$$
\begin{align}
Q(w)+\lambda \lvert \lvert w \rvert  \rvert _{1 }\to min \quad \implies \\
\implies\begin{cases}
Q(w) 0> \min\limits_{w} \\
\lvert \lvert w \rvert  \rvert _{1}\leq C
\end{cases}
\end{align}
$$
![[Pasted image 20231006114930.png]] 

#### Some other reason, why does this work?
$$
\begin{align}
w &= (1, \epsilon) \\
\lvert \lvert w - (\delta, 0) \rvert  \rvert_{2}^2  &= 1 - 2\delta + \delta^2 + \epsilon^2 \\
\lvert \lvert w-(\delta,0) \rvert  \rvert &= 1 - \delta + \epsilon  \\
\lvert \lvert w - (0, \delta) \rvert  \rvert_{2}^2 &= 1 - 2\epsilon\delta + \delta^2 + \epsilon^2 \\
\lvert \lvert w - (0, \delta) \rvert  \rvert_{1} &= 1 - \delta + \epsilon  
\end{align}
$$
L1 - рег. неважно какой коэффициент приближать к нулю
L2 - рег. выгоднее уменьшать большие коэффициенты

#### Another reason why does this work.
[[Proximity Method]]

$$
\begin{align}
w^{(k)} = S_{\eta\alpha}(w^{(k-1)}-\eta \nabla_{w}Q(w^{(k-1)})) \\
S_{\eta\alpha}(w_{i}) = \begin{cases}
w_{i} - \eta \alpha & w_{i} \geq \eta\alpha \\
0, & \lvert w_{i} \rvert < \eta\alpha \\
w_{i} + \eta\alpha , & w_{i} \leq - \eta\alpha 
\end{cases}
 \\
\end{align}
$$
Это уравнение решает задачу минимизации L1
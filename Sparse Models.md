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
Q(w) 0> min_{w} \\
\lvert \lvert w \rvert  \rvert _{1}\leq C
\end{cases}
\end{align}
$$
![[Pasted image 20231006114930.png]]
## Definition
$\exists \;u_i,u_j: \quad  \sigma^{2}_{u_{i}}\neq \sigma^{2}_{u_{j}}$ 

where $u_{i}, u_{j}$ are errors on objects $X_{i}, \;X_{j}$


## Related:
[[Homoskedasticity]]


## More info
Property of an estimator for which 3rd assumption of [[Gauss Markov Assumptions For Best Unbiased Estimator]]
is wrong: 
$Var(\epsilon_{i})= \sigma_{i}^{2} = a \cdot f(x_{1},\dots,x_{3},x_{5}^{2})$
then to make variance constant:
$$\frac{Var(\epsilon_{i})}{\sqrt{ f(\dots) }} = a$$


## Tools to fight it
-  vcovHAC / vcovHC
- 
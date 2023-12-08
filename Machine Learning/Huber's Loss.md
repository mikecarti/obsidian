![[Pasted image 20231208022909.png]]

$$
L_{\beta}(y,z) = \begin{cases} 
\frac{1}{2}(y-z)^2&, |y-z| <\beta \\
\beta\left( |y-z|-\frac{1}{2}\beta \right)& , |y-z| >\ \beta
\end{cases}
$$
$\beta$ - гипер-параметер
В точках перехода проблемы с производной.
### Motivation
Let us take the best from both worlds (MAE, MSE).
While [[MSE]] is  [[Arithmetic Mean]]-[[Unbiased Estimator]] and [[MAE]] is [[Geometric Mean]]-[[Unbiased Estimator]], first one has disadvantage of being dominated by [[Outliers]]. So huber's loss is an unbiased estimator in both arithmetic and geometric-mean logics.


![[Pasted image 20230915121057.png]]

As $\beta$ gets bigger, then bigger errors we do not count as [[Outliers]]. We move the point of transition from MSE-like graph to MAE-like graph.

There is a problem with second derivative, BUT we can FIX THAT ALSO by [[Log-Cosh]]

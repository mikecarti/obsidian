
# Definition
$$
E(Y|\bar{X}) = f(\bar{X}) 
$$
where $\bar{X}$ is a vector.

$$
a(x) = w_{0} + \sum_{j=1}^{d}w_{j}x_{j} \text{  - linear regression model}
$$
$w_{0} - \text{free coefficient (bias intercept)}$
$w_{j} - \text{coefficient weights}$

### Vector representation
$$
x = \begin{bmatrix}
x_{1} \\
\dots \\
x_{d}
\end{bmatrix} \in \mathbf{R}^d   \;\;\;\; w = \begin{bmatrix}
w_{1} \\
\dots \\
w_{d}
\end{bmatrix} \in \mathbf{R}^d
$$
$a(x) = w_{0}+<w,x>$
Assumption: we have a constant feature $x_{1}\equiv1$. Then we do not need $w_{0}$. Therefore:
$a(x) = <w,x>$

## Applications of linear models
$a(x) = w_{0}+w_{1} \cdot \text{area} + w_{2} \cdot \text{floor}+w_{3} \cdot \text{(dist. from. metro)}$

- Features influence target independently. (Assumption of independent variables $x$. But that is not good sometimes.)
- Features influence target linearly. 
$\implies$ **For linear models data must be PREPARED**

### [[Categorical features]]
$a(x)= w_{0}+w_{1} \cdot \text{[хамовники]}+w_{2} \cdot \text{[басманная]}+\dots$
### [[Feature Discretization]]
### [[Polynomial features]]
area - $x_{1}$
floor - $x_{2}$
dist. - $x_{3}$

$x_{1}^2, x_{2}^2, x_{3}^5$
### Further down the road of func. insanity:
$\sqrt{ x_{1}}, \sin(x_{2}), \log_{x_{3}}, \dots$



## Why linear regression is called like that?
$$
\frac{dY}{d\beta_{\dots}} = c
$$
where $c$ does not depend on $\beta\dots$


## Minimization of errors (OLS)
$$
e_{i} = Y_{i} - (\hat{\beta}_{0}+\hat{\beta}_{1}x_{i})
$$
$$
\sum_{i=1}^{n}{e_{i}^2}\to \min\limits_{\beta_{0}, \beta_{1}}
$$
*Note*: Residuals are not errors. Errors are R.V. Residuals are just numbers. Do not confuse them. 


### Residual sum of squares 
$$
\text{RSS} = \sum_{i=1}^{n}e^2_{i}
$$

### Error sum of squares
$$
\text{ESS} = \sum_{i=1}^{n}(\hat{y}_{i}-\bar{y})
$$



## [[Multicollinearity]] 
If features are colinear, if you can exchange time for quality, dont take away colinear features.
Theoretical weights ($beta$) solving
$$
\beta = (E[XX^T])^{-1}Xy
$$
In case if matrix is singular, then we may use
"Moore-Pemrose inverse"
"Pseudoinverse"

### EPE(f) (Expected loss to be minimized by choosing the right model $f$)
 $$EPE(f) = E \left[ L(y,f(X)) \right] = E\left[ (y − f(X))^2\right] \to \min_{f}.$$
 



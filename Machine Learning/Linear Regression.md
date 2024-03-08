
## Definition:
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

## Examples:
### [[Categorical features]]
$a(x)= w_{0}+w_{1} \cdot \text{[хамовники]}+w_{2} \cdot \text{[басманная]}+\dots$
### [[Polynomial features]]
area - $x_{1}$
floor - $x_{2}$
dist. - $x_{3}$

$x_{1}^2, x_{2}^2, x_{3}^5$
### Further down the road of function insanity:
$\sqrt{ x_{1}}, \sin(x_{2}), \log_{x_{3}}, \dots$
Problem: not clear which function to take.


## Why linear regression is called like that?
$$
\frac{dY}{d\beta_{\dots}} = c
$$
where $c$ does not depend on $\beta\dots$


## Measurement of errors in regression task
$$
L(y,z)
$$
$y$ - ground truth
$z$ - prediction

$Q(a,X) = \frac{1}{l}\\sum_{i=1}^{l}L(y_{i}, a(x_{i}))$

# Unobserved variables (Disturbance / Error term)
In econometric sense, linear regression model can be viewed as:
$$
y = \beta_{0} + \beta_{1}x_{1} + \dots + \beta _{n}x_{n} + u
$$
Where $u$ is the disturbance term. 
## Main Assumption of Disturbance
$$
E(u\mid x) = E(u \mid x_{1}, \dots, x_{n}) = E(u)
$$
That assumption implies: observed variables are independent of unobserved. 

## Zero Mean Assumption of Disturbance
$$
E(u) = 0
$$



Related:
1) [[Metrics and Loss Functions]]
2) [[Multicollinearity]]
3) [[Expected Probability Error (EPE)]]
4) [[Ordinary Least Squares (OLS)]]
5) [[Feature Discretization]]
6) [[Simple Linear Regression]]





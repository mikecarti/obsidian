
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
### Mean Squared Error
$$
L(y,z) = (y-z)^2
$$
$$
Q(a, X)=\frac{1}{\ell}\sum_{i=1}^{\ell}(a(x_{i})-y_{i})^2 : \text{MSE}
$$
![[Pasted image 20230915114953.png|400]]
(*квадратные рубли*)

#### RMSE
$$
RMSE = \sqrt{ \frac{1}{\ell}\sum_{i=1}^{\ell}(a(x_{i})-y_{i})^2 } = \text{Real values (not)}^2
$$
#### $R^2$
$$
R^2 = 1 - \frac{\sum_{i=1}^{\ell}(a(x_{i})-y_{i})^2}{\sum_{i=1}^{\ell}(y_{i}-\bar{y})^2}
$$
(coefficient of determination)

$$
\begin{align}
a(x_{i})=y_{i} \implies R^2=1 \\
a(x_{i})=\bar{y} \implies R^2=0
\end{align}
$$
For reasonable models $0< R^2 \leq 1$

#### MAE
$$
L(y,z)=\mid y-z\mid
$$
$$
MAE=\frac{1}{\ell}\sum_{i=1}^{\ell}\mid a(x_{i}-y_{i})\mid
$$
![[Pasted image 20230915115837.png]]

![[Pasted image 20230915120045.png]]

[[Linear Regression#Mean Squared Error |MSE]] стимулирует подгонку под выбросы (сильнее парится по поводу объектов, на которых вы сильно ошибаетесь)
[[Linear Regression#MAE|MAE]] лучше игнорирует выбросы

Then, why we do not use [[Linear Regression#MAE|MAE]] all the time?
1) It may be good to штрафовать for big errors
2) On [[Linear Regression#Mean Squared Error |MSE]], we can get [[Gradient]] and understand how CLOSE we are to extremum. So using [[Linear Regression#MAE|MAE]] we can not understand how far we from the minimum

#### Huber's loss
Let us take the best from both worlds
$$
L_{\beta}(y,z) = \begin{cases} \\
\frac{1}{2}(y-z)^2&, |y-z| <\beta \\
\beta\left( |y-z|-\frac{1}{2}\beta \right)& , |y-z| >\ \beta
\end{cases}
$$
$\beta$ - гипер-параметер
В точках перехода проблемы с производной

![[Pasted image 20230915120915.png]]


![[Pasted image 20230915121057.png]]

as $\beta$ gets bigger, then bigger errors we do not count as [[outliers]]. We move point of transition from MSE-like graph to MAE-like graph.
### Minimization of errors (OLS)
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
 



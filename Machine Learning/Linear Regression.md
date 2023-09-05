
# Definition
$$
E(Y|\bar{X}) = f(\bar{X}) 
$$
where $\bar{X}$ is a vector.


# Why linear regression is called like that?
$$
\frac{dY}{d\beta_{\dots}} = c
$$
where $c$ does not depend on $\beta\dots$




### [[Multicollinearity]] 
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
 



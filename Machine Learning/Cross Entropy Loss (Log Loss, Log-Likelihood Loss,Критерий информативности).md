## Definition
$$
H(X):= -\sum_{x \, \in \,X} p(x) \log q(x) = -E\left[ \log q(x) \right] 
$$
$p(x)$ - true distribution
$q(x)$ - predicted distribution

### Binary Classification
$$
\begin{align}
H(X) = \sum_{i=1}^{l}\left( -\left[ y_{i}=+1 \right] \log b(x_{i})-\left[ y_{i}=-1 \right] \log(1-b(x_{i})) \right)
\end{align}
$$

#### Other names
- Focal Loss
- Kullback-Leibler Divergence Loss (KL Divergence) 
- Negative Log-Likelihood Loss


### Derived from:
 [[Maximum Likelihood Estimation (MLE)]]

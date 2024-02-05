## Definition
$$
H(X):= -\sum_{x \, \in \,X} p(x) \cdot \log p(x) = -E\left[ \log p(x) \right] 
$$
$p(x)$ - predicted value

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

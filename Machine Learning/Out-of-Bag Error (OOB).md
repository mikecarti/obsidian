
$$
OOB = \frac{1}{l}\sum_{i=1}^{l}L\left( y_{i},\underbrace{  \frac{1}{\sum_{n=1}^{N}\left[ x_{i}\neq X_{n} \right] }\sum_{n=1}^{N}\left[ x_{i}\neq X_{n} \right] b_{n}(x_{i}) }_{ \text{Prediction for }x_{i} \text{ produced by trees, that didnt train on }x_{i} } \right) \approx LOO
$$
Where LOO is a [[Leave One Out Error (LOO)]]. That is [[K-Fold Cross Validation]], where 
k of folds $=$ number of objects.
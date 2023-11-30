is a [[Bagging]] made of [[Decision Tree|Decision Trees]]. The most multi-purpose method in machine learning.

1) Trees are being trained as deep as possible (min_samples_leaf=3)
2) Trees are trained on [[Bootstrap]] samples. (or any sub-sample)
3) In each node in $[x_{j}\geq t]$ select $j$ from random subset of features with size $k$. Each node has THEIR OWN subset.

Own sub-sample of features for every tree. Therefore some trees would not be trained on important features. $\implies$ $b_{i}(x)$ will not have important feature $\implies$ $bias(b_{i})\uparrow$ $\implies bias(a_{N}) \uparrow$

classification: 
$$
arg\max_{y\, \in \,\mathbb{Y}} \sum_{n=1}\left[ b_{n}(x)=y \right] 
$$
regression:
$$
\frac{1}{N}\sum_{n=1}^{N}b_{n}(x)
$$

Authors advice to take these values:
Classification: $k=[\sqrt{ d }]$
Regression: $k=\left[ \frac{d}{3} \right]$
### Only one Hyper-Parameters
N - number of trees.

![[Pasted image 20231127232543.png|500x200]]

### Caveats:
1) Very big training time.
2) If $bias(b_{n})\gg 0$, then RF will be bad (for. example more features than observations)

### RF: out-of-bag
$b_{n}(x)$ is trained on $X_{n} \subset X$. Then every tree has objects that were not seen in the time of training. [[Out-of-Bag Error (OOB)]]


### RF: Features Importance
([[Permutation Feature Importance]]) 
(Can be used not only for Random Forest)

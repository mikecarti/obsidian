$y_{i}$ - correct cluster
$a(x_{i})$ - cluster from model

Correctness:
$$
c(x_{i}, x_{j}) = [y_{i}=y_{j}][a(x_{i})=a(x_{j})]
$$

Precision - BCubed 
$$
PB^{3} = \frac{1}{l}\sum\limits_{i=1}^{n}\left( Avg_{x_{j}\; \mid\; a(x_{i})=a(x_{j})} \quad  C(x_{i},x_{j}) \right) 
$$
Recall - BCubed = 
$$
RB^{3} = \frac{1}{l}\sum\limits_{i=1}^{l}\left(  Avg_{{x_{j}\;\mid\; y_{i}=y_{j}}} \quad C(x_{i},x_{j})\right) 
$$

$$
F_{BCubed} = \frac{2precision - recall}{precision - recall}
$$
Does fit all assumptions from [[Extrinsic Clustering Metrics|here]].
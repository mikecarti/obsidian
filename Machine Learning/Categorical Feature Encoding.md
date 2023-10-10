#### 1) One-hot-encoding (OHE)
$x_{j} \to b_{1}(x), \dots, b_{m}(x_{j})$
$b_{i}(x_{j}) = [x_{j} = c_{i}]: bool$

(Ayverson Notation $[u] = 1, [u]= 0$)

#### 2) One-cold-encoding
is an inverse thing of OHE.


#### 3) [[Mean Target Encoding (MTE)]]

#### 4) Counters
(popularity of a class)
$$
g_{j}(x, X) = \sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{i}(x)]
$$
#### 5) Weight of Evidence (binary classification)
Similar with [[Mean Target Encoding (MTE)]]. How many of positive class there is within some categorical feature value.
$$
\begin{align}
P(c \; | \; y = b) =\frac{{ \sum_{i=1}^{\ell}(y_{i}=b)(f_{j}(x_{i})=c) + \alpha }}{ \sum_{i=1}^{\ell}[y_{i}=b]+2\alpha} \\
y_{j}(x, X) = \log\left( {\frac{P(f_{j}(x)|y=+1)}{P(f_{j}(x)|y=-1)}} \right)
\end{align}
$$

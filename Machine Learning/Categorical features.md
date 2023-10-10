$x_{j}$ - categorical if $x_{j} \in {c_{1},\dots,c_{m}}$


## Encodings
#### 1) One-hot-encoding (OHE)
$x_{j} \to b_{1}(x), \dots, b_{m}(x_{j})$
$b_{i}(x_{j}) = [x_{j} = c_{i}]: bool$

(Ayverson Notation $[u] = 1, [u]= 0)

#### 2) One-cold-encoding
is an inverse thing of OHE.


#### 3) [[Mean Target Encoding (MTE)]]

#### 4) Counters
(popularity of a class)
$$
g_{j}(x, X) = \sum_{i=1}^{\ell}[f_{j}(x_{i})=f_{i}(x)]
$$

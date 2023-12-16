Training of n-th model
$$
\sum_{i=1}^{l} L\left(  y_{i}, a_{N-1}(x_{i})+b_{N}(x_{i})\right) \to \min_{_{b_{n}}} 
$$
[[Taylor Expansion]] can be applied to make this function simpler. Center in $a_{N-1}(x_{i})$.

$$
\begin{align}
&= \sum_{i=1}^{l}(\cancelto{ \text{not depend on } b_{N} }{  L(y_{i},a_{N-1}(x_{i})) }+ \underbrace{ \frac{ \partial  }{ \partial z }L(y_{i},z) \mid_{z=a_{N-1}(x_{i})} }_{ -s_{i} }  b_{N}(x_{i}) +  \\ \\

&\frac{1}{2}\frac{ \partial^{2}  }{ \partial z^{2} } \underbrace{ L(y_{i}, z)\mid_{z=a_{N-1}(x_{i})}b_{N}^{2}(x_{i}) }_{ h_{i} }) = \\
&=\sum_{i=1}^{l}\left( -s_{i}b_{N}(x_{i}) + \frac{1}{2}h_{i}\;b_{N}^{2}(x_{i}) \right) \to \min_{b_{N}}
\end{align}
$$

From classical gradient boosting:
$$
\begin{align}
&\sum_{i=1}^{l}(s_{i} - b_{N}(x_{i}))^{2} = \sum_{i=1}^{l}\left( b_{N}^{2}(x_{i})- 2s_{i}b_{N}(x_{i}) + \cancel{ s_{i}^{2} } \right) =   \\
&=\{ /2 \} = \sum_{i=1}^{l} \left( -s_{i}b_{N}(x_{i})+\frac{1}{2}b_{N}^{2} (x_{i}) \right)\to \min_{b_{N}}
\end{align}
$$

Second [[Derivative]] represents curviness of my loss function, it can be useful sometimes.

On differentiation of this thing later will be written.
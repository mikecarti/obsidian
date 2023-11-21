



## [[Decision Tree|Trees]] Ensemble
Problem: Low variation in dataset, results in very high variation in decision trees
Idea: What if we average predictions in these decision trees?

[[Bootstrap]]: generation of subsample from $X$ samples, $l$ objects with returning
$$
\{ 1,2,3,4 \}\to \{ 1,2,2,4 \}
$$
$X\to \underbrace{ X_{1} }_{ b_{1}(x) },\dots \underbrace{ X_{N} }_{ b_{N}(x) }$ - sub-samples
$y(x)$ - true answer
$p(x)$ - density on $\mathbb{X}$
$\epsilon_{j}(x)=b_{j}(x)-y(x)$
$E_{x}(b_{j}(x)-y(x))^{2}=\mathbb{E}_{x}\epsilon_{j}^{2}(x)=E_{1}$            (mse)
Assumptions: 
- $\mathbb{E}[\epsilon_{j}(x)]=0$                     (unbiasedness)
- $\mathbb{E}\left[ \epsilon_{i}(x)\epsilon_{j}(x)\right]=0, i\neq j$   (uncorrelatedness)
$$
\begin{align}
&a(x) = \frac{1}{N}\sum_{j=1}^{N}b_{j}(x) \\
&\mathbb{E}\left(\frac{1}{N}\sum_{j=1}^{N}b_{j}(x)-y(x)   \right)^{2}  = \mathbb{E}\left( \frac{1}{N}\sum_{j=1}^{N}b_{j}(x)- \frac{1}{N}\sum_{j=1}^{N}y(x) \right)^{2}= \\
&= \mathbb{E}\left( \frac{1}{N}\sum_{j=1}^{N}\epsilon_{j}(x) \right)^{2} = \frac{1}{N^{2}}\mathbb{E}\left( \sum_{j=1}^{N}\epsilon_{j}^{2}(x) + \cancelto{ 0 }{ \sum_{i\neq j}\epsilon_{i}(x)\epsilon_{j}(x) } \right)   = \\
&=\frac{1}{N^{2}}\sum_{j=1}^{N}\underbrace{ \mathbb{E}(\epsilon_{j}^{2}(x))U }_{ E_{1} } = \frac{1}{N^{2}}N  \cdot  E_{1} = \frac{E_{1}}{N} \text{ - error diminished in N times}!!!
\end{align}
$$


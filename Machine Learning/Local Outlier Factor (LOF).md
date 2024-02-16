anomaly detection.

Idea:
Compare
(distance from x to its nearest neighbors)
and
(distance from nearest neighours to THEIR nearest neighbors)
![[Pasted image 20240216120029.png]]



reachability distance $:=rd_{k}(x,z) = max(\rho_{k}(z), \rho(x,z))$ 
$\rho_{k}(z)$ - distance from $z$ to $k$-th nearest neighbor 

this rd gives us some stabilization in case 2 objects are rarely close to each other
![[Pasted image 20240216120047.png]]



$$
\begin{align}
lrd_{k}(x) = \frac{1}{\frac{1}{k}\sum_{z\, \in \,\mathcal{N}_{k}(x)}rd_{k}(x,z)}
\end{align}
$$
$lrd$ - local reachability distance
$\mathcal{N}_{k}(x)$ - set of $k$ nearest neighbors for $k$.
![[Pasted image 20240216120645.png]]

$$
\begin{align}
LOF_{k}(x) = \frac{{\frac{1}{k}\sum_{z \, \in \, \mathcal{N}_{k}(x)}lrd_{k}(z)}}{lrd(x)} \\
LOF_{k}(x) > 1 \implies \text{density for neighors x is higher} \\
\text{than that x } \implies anomaly \\
LOF_{k}(x) < 1 \implies \text{inside of an area}
\end{align}
$$
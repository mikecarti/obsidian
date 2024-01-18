## Definition
$$
f(X=k) = {\displaystyle {\frac {\lambda ^{k}e^{-\lambda }}{k!}}} 
$$
For $k$ occurrences where $\lambda$ - mean occurrences . 

## Expected value & Variance

$$
E[X_{t}] = Var[X_{t}]=\lambda t
$$
$$
P[X(t+s)−X(s)=n]=P[P_{0}(λt)=n]=\frac{e^{-\lambda t}{(\lambda t)^{n}}}{n!}
$$

### No occurrences in an interval:
$$
\begin{align}
X_{t+h}-X_{t} \sim Poisson(rate=h\lambda) \\
P(X_{t+h}-X_{t}=0)=e^{-\lambda h}
\end{align}
$$
### K occurrences in an interval:
$$
P(X_{t+h}-X_{t}=k)=P(X_{h}-X_{0}=k)= \exp(-\lambda h) \cdot \frac{(\lambda h)^{k}}{k!}
$$


Where $X_{t}$ - number of events happened in $t$ time.

![[Pasted image 20230922162547.png]]
## Counting Process
![[Pasted image 20230922162748.png]]
For example, $X_{S_{3}}= 3$

$$
(X_{t}) \;\;\;\;\;\;\;\;\; t \in [0; \infty] \text{ and } x_{t} \in \{ 0,1,2,3,\dots \}
$$
#### Assumptions
-  $X_{0}=0$
- Independent increments (may not overlap, but may touch)
$N_{1}=X_{b_{1}}-X_{0_{1}}$
$N_{2}=X_{b_{2}}-X_{0_{2}}$                            $N_{k}$ - the num. Of arrivals in interval k.
$\vdots$
- Stationary increments
The distribution of $N_{k}$ depends only on the length of the time interval.
$(X_{t+h} - X_{t}) \sim Law(h)$

-  1 Arrival
$P(X_{t+h}-X_{t}=1)$ is approximately proportional to the $h$ (1 arrival)
$P(X_{t+h}-X_{t}=1)=\lambda h + o(h)$ for small $h$
- 2 Arrivals
$P(X_{t+h}-Xt\geq 2)$ is negligible (insignificant) compared to $h$
$P(X_{t+h}-X_{t})=o(h)$ for small $h$

##### Based on these assumptions, we get powerful result:
$T_{k} \sim Exp(rank=\lambda)$
$\underbrace{ X_{t+h}-X_{t}\ }_{ \text{number of arrivals in [t+h]} } \sim Poiss(rate=\lambda h)$

$T_{k}$ - interarrivals (time between arrival of person k-1 to k)

##### Property 1
If P.P ($X_{t}$)  and $(Y_{t})$ are indep. Then 
$Z_{t}=X_{t}+Y_{t} \sim PP$
$(\lambda_{z}=\lambda_{x}+\lambda_{y})$
##### Property 2
$P(T_{1}^{x}<T_{1}^{y})=\frac{\lambda_{x}}{\lambda x+\lambda y}$



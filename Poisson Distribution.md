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
$N_{2}=X_{b_{2}}-X_{0_{2}}$                            $N_{k}$ - the num. of arrivals in interval k.
$\vdots$
- Stationary increments
The distribution of $N_{k}$ depends only on the length of the time interval.
$(X_{t+h} - X_{t}) \sim Law(h)$

-  1 Arrival
 $P(X_{t+h}-X_{t}=1)$ is approximately proportional to the $h$ (1 arrival)
$P(X_{t+h}-X_{t}=1)=\lambda h + o(h)$ for small $h$
- 2 Arrivals
-  $P(X_{t+h}-Xt\geq 2)$ is negligible (unsignificant) compared to $h$
$P(X_{t+h}-X_{t})=o(h)$

##### Based on this assumptions:
$T_{k} \sim Exp(rank=\lambda)$
$X_{t+h}-X_{t}\sim Poiss(rate=\lambda h)$

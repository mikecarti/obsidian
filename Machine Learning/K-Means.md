## Formal Definition
$K$ - Hyperparameter.
$$
\sum_{k=1}^{K}\sum_{i=1}^{l}\left[ a(x_{i})=k \right] \; \rho(x_{i}, c_{k}) \to \min_{}
$$
Idea: sequentially optimize for $a(x)$ and $c_{k}$

**Step 0** Initialize centroids (for example [[K-Means++]])
**Step a** Fix $c_{k}$ (centroids)
$$
a(x_{i}) = \operatorname*{argmin}_{k=1,\dots,K} \;\rho(x_{i}, c_{k})
$$
**Step b** Fix $a(x_{i})$
$$
c_{k}= \operatorname*{argmin}_{c \, \in \,\mathbb{X}} \sum_{a(x_{i})=k}\rho(x_{i}, c)
$$
If $\rho(x, c)= \lvert\lvert x-c \rvert\rvert_{2}^{2}$ , then:
$$
c_{k} = \frac{1}{\sum_{i=1}^{l}\left[ a(x_{i})=k \right] }\sum_{i=1}^{l}\left[ a(x_{i})=k \right]x_{i} 
$$
**Step c** If converged:
				break
			else:
				Go to **Step a** 

### Pros and Cons
+ + fast
+ + parallelizable
+ - strongly depends on good initialization
+ - different scales of features can break algorithm
+ - very simple forms of clusters (round/ ellipsoid)
### illustration
![[Pasted image 20231213172258.png]]

![[Pasted image 20231213172305.png]]

![[Pasted image 20231213172315.png]]

![[Pasted image 20231213172336.png]]

![[Pasted image 20231213172350.png]]
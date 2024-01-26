Karush Kuhn Tucker Conditions. Условия дополнительной нежесткости. 

![[Lagrangian##Definition]]


Given
$$
\begin{align}
&\min_{}f_{0}(x) \\
&f_{i}(x)\leq 0, \quad  f_{j}(x)=0
\end{align}
$$

The KKT conditions are:
## Stationarity
$$
0 \, \in \partial f(x)+ \sum_{i=1}^{m}\lambda_{i}\partial h_{i}(x)+ \sum_{j=1}^{r}v_{j}\partial \ell_{j}(x)
$$
## Complementary Slackness
$$
\lambda_{i}h_{i}(x)= 0 \quad  \forall i
$$
## Primal Feasibility
$$
	h_{i}(x)\leq 0, \quad  \ell_{j}(x)=0 \quad \forall i,j
$$
## Dual Feasibility
$$
\lambda_{i}\geq 0 \quad \forall i
$$


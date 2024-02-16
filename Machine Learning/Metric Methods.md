# Anomaly Detection
Hypotheses: object is an anomaly if in $X$ there is no close to it objects.

Base approach:   $x_{(1)}, \dots, x_{(k)}$ - nearest objects to x from training set $X$
$$
\begin{align}
\frac{1}{k}\sum_{i=1}^{k} \rho(x,x_{(i)}) \geq \alpha \text{ anomaly}
\end{align}
$$

There is a problem, we can not find such $\alpha$ that take into account different density across space.
![[Pasted image 20240216115527.png]]

(1) and (2) have same distance to nearest neighbour => we should take into account that in different areas there can be differenent density

![[Local Outlier Factor (LOF)]]
$$
R^2 = \frac{ESS}{TSS} = 1 - \frac{RSS}{TSS}
$$
### Properties
1) $R^2 \in [0;1]$
2) $R^2 = [corr(x;y)]^2$
3) shows how much of target's variance is explained by independent variables.


### Values of R^2
##### If R^2 $\approx$ 0.999, then...
- You should check for overfitting
- You should check for mistakes while creating the model 
(for example, Profit = Income - Costs)
- Your data is FAKE
##### If R^2 $\approx$ 0.01, then
- It's not always tells that model is bad (but not too good)
- It is okay if $0.1\leq R^2 <= 0.9$


### TSS, ESS and RSS
$$
\begin{align}
TSS = \sum(y_{i}-\bar{y})^2 = \sum(\hat{y}_{i}-\bar{\hat{y}})^2+\sum e_{i}^2 \\
ESS
\end{align}
$$$$
\begin{align}
TSS = ESS + RSS  
\end{align}
$$(Total SS, Explained SS, Residual SS)

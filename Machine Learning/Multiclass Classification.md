$$
\mathbb{Y} = \{ 1, \dots, K \} \text{ (K - number of classes)}
$$

## Reduction to class of [[Binary Classification]] tasks:
### One vs All (OVA)
$$
\begin{align}
b_{k}(x)= \left< w_{k}, x \right> + w_{0k} \\
\text{train }b_{k}(x): \quad X_{k} = (x_{i}, \left[ y_{i}=u \right] )_{i=1}^{l} \\
a(x)= argmax_{k:1,\dots,K}( b_{k}(x) )
\end{align}
$$
+: easy
-: a lot of classes -> a lot of parameters (k(a+1))
-: $b_{k}$ know nothing about each other during training

### All vs All (AVA)
![[Pasted image 20231103122604.png]]

$$
\begin{align}
C_{k}^{2} \text{ - classifier} \\
a_{ij}(x) \text{ - training} \\
X_{ij}= \{ (x_{n,}y_{n})\mid y_{n}\in\{ i,j \} \} \\
a(x) = argmax_{k=1,\dots K} \sum_{j\neq k}\left[ a_{kj}(x)=k \right] 
\end{align}
$$
+: no troubles with non-calibrated probabilities
-: a lot of parameters ($\sim K^{2}$)


## Direct Approach methods
### Multiclass Linear Regression
$$
\begin{align}
b_{k}(x)= \left< w_{k}, x \right> + w_{0k} \\
x \to b(x) = \left( b_{1}(x), \dots, b_{k}(x) \right) \\
\mathbb{P}(y=k|x) = \frac{{\exp(\left< w_{k},x \right> + w_{0k})}}{\sum_{j=1}^{k} (\left< w_{j},x \right> + w_{0j} )} 
\end{align}
$$
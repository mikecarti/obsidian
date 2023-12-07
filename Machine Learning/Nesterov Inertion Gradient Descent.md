Same as [[Gradient Descent with Momentum]], but we do inertion step first, then we do gradient step. By that we better acknowledge loss function and faster converge. 

$$
h_{k}= \alpha h_{k-1} + \eta_{k}\nabla Q(w^{(k-1)}-\alpha h_{k-1})
$$

## Gradient boosting 
$$
\begin{align}
h_{0}(x)=a_{0}(x)=b_{0}(x) \\
a_{N-1}(x), h_{N-1}(x) \\
s_{i}= -\frac{ \partial  }{ \partial z }L(y_{i},z)\mid_{z=a_{N-1}(x_{i})+\alpha h_{N-1}(x_{i})} 
\end{align}
$$
![[Pasted image 20230929174357.png]]
$$
\begin{equation} RELU(x) = \begin{cases} 0 & \text{for } x \leq 0 \\ x & \text{for } x > 0 \end{cases} \end{equation}
$$
Very fast gradient. So it is more popular than [[Sigmoid]] 

## Null gradients for negative inputs
Lower values than 0 provide Null derivative, so that is solved in [[Leaky RELU]]
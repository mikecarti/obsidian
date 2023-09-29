![[Pasted image 20230929173720.png]]

$$
\begin{align}
y(x) &= \frac{1}{1+e^{-x}} \\
\end{align}
$$


## Problem:
Can not train very deep [[Neural Network|Neural Networks]]. 

$$
\begin{align}
\frac{dy}{dx} &= y(x) \cdot (1-y(x)) \\
u &= W_{i}z_{i} + b_{i} \\
z_{i+1} &= y(u_{i}) \\
\frac{dl}{dz_{i}} &= \frac{dl}{dz_{i+1}} \cdot \underbrace{ y'(u_{i}) }_{ \approx 0 \text{ for } i > N }\left( \frac{du_{i}}{dz_{i}} \right)
\end{align}
$$



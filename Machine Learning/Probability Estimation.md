$$
arg\min_{b\, \in \,\mathbb{R}} \mathbb{E}_{y}(L(y,b)\mid x\mid)= p(y=+1\mid x)
$$

### Bad example:
$$
\begin{gather}
L(y,b) = \mid [y=+1]-b\mid \\
\frac{\delta}{\delta b} = -p(y=+1\mid x) + (1-p ( y=+1 \mid x)=  \\
= 1-2p(y=+1\mid x)=0 \implies \\
\implies \text{оптимум на границе} \implies b_{*} = 0, b_{*} = 1 \\
\implies \text{this loss function does not help in probability estimation}
\end{gather}
$$


### Calibrating Curve
For measuring probability estimation.

![[Pasted image 20231114115121.png]]

B - number of bins - Hyperparameter

#### ECE (Expected Calibration Error)
$$
ECE = \frac{1}{B}\sum_{i=1}^{B}\left( \frac{1}{\mid B_{i}\mid }\sum_{(x_{i}, y_{i})\, \in \,B_{i}}b(x_{j}) - \frac{1}{\mid B_{i}\mid}\sum_{(x_{i},y_{i})\, \in \,B_{i}}\left[ y_{i}=+1 \right]  \right) 
$$

### Types of calibration
- [[Platta Calibration]]
- [[Isotonic Regression]]
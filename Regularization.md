#### Famous experimental fact: 
If a linear model is over-trained $<==>$ it has large weights.

#### Why?

1. Imagine we have some linearly dependent features
$$
\begin{gather}
\exists v \in \mathbb{R}^{d}: \forall x \in \mathbb{X} \qquad <u, x> = 0 \\
w_{ * } - \text{solution} \qquad \frac{1}{l}\sum_{i=1}^{l}(<w,x>-y_{i})^{2 } \to min \\
<w_{*} + \alpha u, x> = <w_{*}, x> + \alpha <u, x> = <w_{*}, x> \\
\text{therefore } w_{*} + \alpha u - \text{ one more solution}
\end{gather}
$$
2. hypersensitivity in features - is not like world works
$a(x) = 10^{8}  \cdot \text{area} + 10^{9} \cdot \text{floor} + 10^{11} * \text{hamovniki} + ..$
$10^{8}(\text{area}+0.001)= 10^{8} \cdot \text{area}+10^{8} \cdot 0.001 \approx 10^{8} \cdot \text{area} + 10^{5}$
А просто например штукатурка отвалилась в квартире...

## Idea: Prohibit big weights

$$
\begin{align}
&Q(w) \text{ - error metric} \\
&Q(w)+\alpha R(w) \to min \qquad \text{R(w) - regularization} \\ \\

&R(w) = \lvert \lvert w \rvert  \rvert^{2}_{2}= \sum_{i=1}^{d}w_{j}^{2} \text{ - L2 regul.}  \\
&R(w) = \lvert \lvert w \rvert  \rvert_{1}= \sum_{i=1}^{n}\lvert w_{j} \rvert \text{ - L1 regul.}  \\
&\alpha \text{ - regularization coef.}
\end{align}
$$
Never maximize $\alpha$ based on training data, always on test data - [[Hyperparameters]]


### Strategies for finding $a$ :
1. [[Grid Search]]
2. Random Search
3. AutoML

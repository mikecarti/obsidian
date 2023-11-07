#### Famous experimental fact: 
If a linear model is over-trained $<==>$ it has large weights.

#### Why?

1. Imagine we have some linearly dependent features
$$
\begin{gather}
\exists v \in \mathbb{R}^{d}: \forall x \in \mathbb{X} \qquad <u, x> = 0 \\
w_{ * } - \text{solution} \qquad \frac{1}{l}\sum_{i=1}^{l}(\left< w,x \right> -y_{i})^{2 } \to min \\
\left< w_{*} + \alpha u, x \right>  = \left< w_{*}, x \right>  + \alpha \left< u,x \right>  = \left< w_{*}, x \right>  \\
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

## Naming:
### Ridge:
$$
\frac{1}{l}\sum_{i=1}^{l}(<w,x_{i}>-y_{i})^{2} + \alpha \lvert \lvert w \rvert  \rvert^{2}_{2} \to min 
$$
![[Pasted image 20230929122150.png|450]]

b) Регуляризация гарантирует, что точно есть решения
$$
\begin{align}
w_{*} =  (X^{T}X+\alpha I)^{-1}X^{T}y \\
aigen(X^{T}X) \geq 0 \\
X^{T}X+\alpha I > 0 \implies invertible \\
\end{align}
$$
![[Pasted image 20230929122446.png|300]]
$\alpha\alpha\alpha\dots\alpha$ - Типа гребень

### LASSO:
Особенность: Lasso зануляет часть весов

## Note 1
![[Pasted image 20230929122859.png]]

So NEVER include $w_{0}$ in regularizator. 

## Note 2
Let us have features of different scale

время поиска конспекта ~ 5-8 минут =0.01 (расст. до кабинета ~ 100метров) *  + 0.0001(минут после хорошего сна ~500.000 минут) 

Штрафую расстояние до кабинета сильнее потому что другой масштаб
----> $\|w| |$ ведет себя неадекватно при немасштабируемом признаке
----> надо масштабировать (тоже ускоряет градиентный спуск)
$$\implies x_{ij}=\frac{{x_{ij}-\mu_{i}}}{s_{j}}$$

## Note 3
Добавление ругуляризатора добавляет градиентный спуск, потому что упрощает рельеф функции потерь

![[Pasted image 20231006113718.png|500]]


## Related:
[[Ridge and Lasso regularization is like a salt in cookery. Often makes model better.]]
[[Linear Regression]]
[[Over-fitting]]

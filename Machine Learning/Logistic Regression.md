### Model
$$
b(x) = \sigma(<w,x>)
$$
is a sigmoid over a distance from hyperplane to an object.



### Loss function
True loss function:
$$
\begin{align}
arg\min_{b\, \in \,\left[ 0,1 \right] } \frac{1}{n}\sum_{i=1}^{n}L(y_{i},b) = \frac{1}{n}\sum_{i=1}^{n}\left[ y_{i}=+1 \right] 
\end{align}
$$

Upper Bound Estimations:
- [[Cross Entropy Loss (Log Loss, Log-Likelihood Loss,Критерий информативности)|Log-Loss]]
$$
\begin{align}
H(X) = \sum_{i=1}^{l}\left( -\left[ y_{i}=+1 \right] \log b(x_{i})-\left[ y_{i}=-1 \right] \log(1-b(x_{i})) \right)
\end{align}
$$
- [[Logistic Loss]]
$$L(y, z) = \log(1 + \exp(-yz))$$
- [[Hinge-Loss]]



## Intuition 
We want to estimate probabilities of classes. 
$a(x)=+1$. And model is confident on 80%. This can be interpreted as follows:
$$
\text{If we take all objects with confidence N\%, than N\% from them will have y = + 1}
$$


## Formalization
$b(x)$ - gives correct probability of positive class.
$b(x) = \sigma(\left< w,x \right>) \, \in \,(0,1)$
$\sigma(z)=\frac{1}{1+\exp({-z})}$

#### Scalar Product
Как при этом можно интерпретировать данное скалярное произведение?
Чтобы ответить на этот вопрос, преобразуем уравнение

$$
    p(y = 1 \mid x)
    =
    \frac{1}{1 + \exp(-\langle w, x \rangle)}.
$$
Выражая из него скалярное произведение, получим
$$

    \langle w, x \rangle
    =
    \log
    \frac{
        p(y = +1 \mid x)
    }{
        p(y = -1 \mid x)
    }.

$$
Получим, что скалярное произведение будет равно логарифму отношения
вероятностей классов~(log-odds).

### Mathematical Reasoning
###### $b(x)$ estimates probabilities, if for probability $p$ among all observations $x \, \in \,\mathbb{X}$ (where $\mathbb{X}$ is the [[Population]]) with $b(x)=p$, proportion of positive observations is equal to $p$.

$$
\begin{align}
&x_{1} =x_{2}=\dots=x_{n} \implies b(x_{1})=\dots=b(x_{n})=b =const \\
&y_{1} \dots y_{2} \dots
\end{align}
$$
###### Would be reasonable to set 
$$
b = \frac{1}{n}\sum[y_{i}=+1]
$$
##### Therefore:
$$
\begin{align}
arg\min_{b\, \in \,\left[ 0,1 \right] } \frac{1}{n}\sum_{i=1}^{n}L(y_{i},b) = \frac{1}{n}\sum_{i=1}^{n}\left[ y_{i}=+1 \right] 
\end{align}
$$
##### What will happen if we $n\to \infty$?
$$
\begin{align}
arg\min_{b\, \in \,\left[ 0,1 \right] } \mathbb{E}_{y}\left( L(y,b)\mid x \right) =p(y=+1\mid x) \quad \quad \forall x \, \in \, \mathbb{X}
\end{align}
$$ That is a claim on loss function, that is needed for this model to work properly.

#### For which Loss Functions this claim is true? 
$$
\begin{align}
&L(y,z) = (y-z)^{2}  \\
& L(y,b)= (b - \left[ y=+1 \right] )^{2} \\ \\

&\text{Proof that it satisfies the claim:} \\
&E_{y}(b - \left[ y=+1 \right] )^{2} = p(y=+1\mid x)(b-1)^{2} + (1-p(y=+1\mid x))(b-0)^{2} \\
&\frac{\delta}{\delta b} = 2p(b-1) + 2(1-p)b = 2pb -2p + 2b -2pb = 0 \\
&b = p(y=+1\mid x) \\ \\

&\text{Therefore MSE will try to correctly estimate probabilities!} \\
&\text{But that is not a very good idea...} \\
&L = \frac{1}{l}\sum_{i=1}^{l}\left( \sigma \left( \left< w,x_{i} \right>  \right)  - \left[ y_{i}=+1 \right] \right)^{2}\to \min_{w} \quad  \\
&\nabla _{w}L= 2  \cdot  (\dots)  \cdot  \sigma'\left( \left< w,x_{i} \right>  \right)  \cdot  \dots \quad  \text{Derivative of a sigmoid??}
\end{align}
$$
![[Pasted image 20231122201702.png|700x250]]
On low values gradient is very close to 0... That causes loss function being stuck.

### Creating a loss function from probabilistic ideas
Every object $y_{i}$ is a random variable that is [[Bernoulli]] Distributed.
$b(x)$ - estimation of probability $p(y_{i}=+1\mid x)$

Then we can write [[Maximum Likelihood Estimation (MLE)]]:
$$
\begin{align}

\prod_{i=1}^{l}b(x_{i})^{\left[ y_{i}=+1 \right] } (1-b(x_{i}))^{\left[ y_{i} =-1\right] } \to \min_{b} \mid \text{apply}\log \\
\sum_{i=1}^{l}\left( -\left[ y_{i}=+1 \right] \log b(x_{i})-\left[ y_{i}=-1 \right] \log(1-b(x_{i})) \right) \to \min_{b}
\end{align}
$$
That is [[Cross Entropy Loss (Log Loss)]]. And for it that claim is correct. 
In our case $b(x)=\sigma(\left< w,x \right>)$.




## Related:
[[Binary Classification]] (More here)
[[Linear Regression]]
[[Probabilistic ML]]
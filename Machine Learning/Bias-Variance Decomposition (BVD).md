```
Оказывается, ошибка любой модели складывается из трех факторов:
сложности самой выборки (NOISE: то что не может объяснить модель), сходства модели с истинной зависимостью (BIAS: насколько модель плохо аппроксимирует данные в среднем) ответов от объектов
в выборке, и богатства семейства (VARIANCE: сколько можно построить разных моделей в одном семействе, насколько модель будет меняться из-за изменения тренировочных данных), из которого выбирается конкретная модель.
Между этими факторами существует некоторый баланс, и уменьшение одного
из них приводит к увеличению другого.

(C) Е. Соколов.
```

Error of every model is decomposed into Bias, [[Variance]] and Noise 

$$
\begin{align}
&\mathbb{E}_{x,y}\left( y-\mathbb{E}\left[ y\mid x \right]  \right) ^{2} - \text{Noise} \\
&\mathbb{E_{x,y}(\mathbb{E}_{\mathbb{X}}}\left[\mu (\mathbb{X})_{(x)}  \right] - \mathbb{E}\left[ y\mid x \right]  )^{2} - \text{Bias}  \\
&\mathbb{E}_{x,y}\left( \mathbb{E}_{\mathbb{X}}\left[ \mu(\mathbb{X})_{(x)} \right] - \mu(\mathbb{X})_{(x)}  \right)^{2} - \text{Variance} \\ \\
&L(\mu ) = \text{Bias + Variance + Noise}
\end{align}
$$
$\mu$ - some Model. $L$ - error of model. 

Bias = How good model performs on average (less = better)
Variance = How much model performs differently based on different datasets (less = more stable)

## Bias
The bigger [[Regularization]] $\implies$ The bigger [[Bias]], the worse model performs
## Variance
The bigger [[Regularization]] $\implies$ The smaller [[Variance]], the better model generalizes

## More theory:
$$
\begin{align}
&X = (x_{i}, y_{i})_{i=1}^{l}, \quad y \, \in \,\mathbb{R}, \text{ (regression)} \\
&p(x,y) \text{ for } \mathbb{X} \times \mathbb{Y} \text{ (assume we know the distribution)} \\
&L(y, a) = (y-a)^{2} \\
&\text{Average Square Risk}: \\
&R(a)= \mathbb{E}_{x,y}\left( y-a(x) \right)^{2} = \int _{\mathbb{X}} \int _{\mathbb{Y}}(y-a(x))^{2}p(x,y)\,dxdy    \\
&\text{then: } a_{*}(x) = \mathbb{E} (y\mid x) = \int _{\mathbb{Y}}y\;p(y\mid x) \, dx  
\end{align}
$$
##### Training Method:
$\mu: \underbrace{ (\mathbb{X}\times \mathbb{Y})^{l} }_{ \text{space of training samples} }\to \underbrace{ \mathcal{A} }_{ \text{ model class} }$
$L(\mu)=\mathbb{E}_{x}\mathbb{E}_{x,y}(y-\underbrace{ \underbrace{ \mu (X) }_{ \text{model} }{(x)} }_{ \text{ model prediction on x} })^{2}$     - error of model on x
$L(\mu)= \mathbb{E}_{x,y}(y-\underbrace{ \mathbb{E}(y(x)) }_{ \text{best model} })^{2} +$          - noise (error of best model, lower bound for  error)
$+ \mathbb{E}_{x}\left( \underbrace{ \mathbb{E}_{x}\mu(X) }_{ \text{average model for all X} }-\mathbb{E}(y\mid x) \right)^{2}$    - bias (shift of average model from the best one, suitability of class of models for a task)
$+ \mathbb{E}_{x}\mathbb{E}_{X}(\mu(X)-\mathbb{E}_{x}\mu(X))^{2}$                    - variance (устойчивость метода обучения, характеристика пере-обученности)

Summarizing:
$$
\begin{align}
&L(\mu)= \mathbb{E}_{x,y}(y-\underbrace{ \mathbb{E}(y(x)) }_{ \text{best model} })^{2} + \mathbb{E}_{x}\left( \mathbb{E}_{x}\mu(X)-\mathbb{E}(y\mid x) \right)^{2} +  \\
&+ \mathbb{E}_{x}\mathbb{E}_{X}(\mu(X)-\mathbb{E}_{x}\mu(X))^{2}
\end{align}

$$


## Practice
#### Task 1
$\mathbb{X}=\mathbb{R}$
$\mathbb{Y}=\mathbb{R}$
$a(x)= wx$, $w\, \in \,\mathbb{R}$

$Q(w)=\sum_{i=1}^{l}(y_{i}-wx_{i})^{2 }+ \lambda w^{2} \to \min_{w}$ 
$$\underbrace{ w(X) }_{ optimal }= \frac{{\sum_{i=1}^{l}x_{i}y_{i}}}{\sum_{i=1}^{l}x_{i}^{2}+\lambda}$$
$\mu(X)_{(x)}=w(X)x$        ($\mu(X) - \text{model fitted on data, }\mu(X)(x) -\text{ prediction}$)
$x_{i}$ - determined
$y_{i} = wx + \epsilon$,    $\epsilon~\mathcal{N}(0, \sigma^{2})$ 

1. Calculate noise, Noise: $\sigma^{2}$
2. Calculate bias
$$
\mathbb{E}\left[ \frac{{\sum_{x_{i},y_{i}}}}{\sum x_{i}^{2}+\lambda}x \right] =\frac{{\sum(x_{i}):\mathbb{E}\left[ f(x_{i}+\epsilon) \right] }}{\dots} = \frac{\sum x_{i}f(x_{i})x}{\sum x_{i}^{2}+\lambda} =\frac{ \alpha \sum x_{i}^{2}}{\sum x_{i}^{2} + \alpha}
$$


#### Task 2 (Нулевой Вариант 4.)
$$
\begin{align}
p(x,y): \; x_{i} \sim Exp(1) \quad p(x) = e^{-x} \\
y_{i} = f(x_{i}), \quad  f(z) = \sum_{j=1}^{N} \mid z-j  \mid \quad  N - \text{fixed} \\
\mu(X)(x)=\bar{X} = \frac{1}{l}\sum_{i=1}^{l}x_{i} \\ \\
\end{align}
$$
Noise here is 0 because if we know x, we know y f(x) - is deterministic
$$
\begin{align}
&y=\mathbb{E}[y\mid x ] \implies \mathbb{E}_{x,y} \left( y-\mathbb{E}[y\mid x] \right)^{2} = 0 \\
&\text{Bias: } \\
&\mathbb{E}_{x}\left[( \mathbb{E}_{\mathbb{X}}\left[ \mu(X)(x) \right] - \mathbb{E}[y\mid x])^{2}\right]   \\
&\mathbb{E}_{\mathbb{X}}\left[ \mu(X)(x) \right] -  \text{функция от x, не от X}\\
&\int f(x,y) \, dx  = F(y) \\
\dots \\ \\
&\mathbb{E}\left[ y\mid x \right]  = \mathbb{E}\left[ f(x)\mid x \right]  = f(x) =  \sum_{j=1}^{N} \mid x-j  \mid  \\
&\mathbb{E}_{x}\left[ \left( 1- \sum_{j=1}^{N} \mid x-j  \mid \right)^{2} \right] = \left\{ x \sim Exp(1) \right\}  =  \\
&= \int _{0}^{\infty}(1-  \sum_{j=1}^{N} \mid x-j  \mid)^{2}e^{-x} \, dx   - \text{ ... done} \\
  \\
&\text{Variance: }  \\
&\mathbb{E}_{\underbrace{ x }_{ \text{забиваем} }}\mathbb{E}_{X}(\mu(\underbrace{ X }_{ \text{не зависит от х} })-\mathbb{E}_{\underbrace{ x }_{ \text{ не зависит от х} }}\mu(X))^{2} = \\ \\
&= \mathbb{E}_{\mathbb{X}}(\bar{x}- \mathbb{E}\left[ \bar{x} \right] )^{2} = Var_{\mathbb{X}}(\bar{X}) =
\end{align}
$$

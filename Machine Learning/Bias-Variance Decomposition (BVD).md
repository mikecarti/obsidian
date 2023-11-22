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

$Q(w)=\sum_{i=1}^{l}(y_{i}-wx_{i})^{2 }+ \lambda w^{2}$
$$\underbrace{ w(X) }_{ optimal }= \frac{{\sum_{i=1}^{l}x_{i}y_{i}}}{\sum_{i=1}^{l}x_{i}^{2}+\lambda}$$
$\mu(X)_{(x)}=w(X)x$        ($\mu(X) - \text{model fitted on data, }\mu(X)(x) -\text{ prediction}$)
$x_{i}$ - determined
$y_{i} = wx + \epsilon$,    $\epsilon~\mathcal{N}(0, \sigma^{2})$ 

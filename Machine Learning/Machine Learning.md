
Space of objects $\mathbf{X}$

Space of targets $\mathbf{Y}$ 

Training sample
$$
\begin{split}
X = \{(x_{i}, y_{i})\}_{i=1}^\ell \\
\ell - \text{training sample size} \\
x_{i} = (x_{i_{1}}, x_{i_{2}}, \dots, x_{i_{n}})
\end{split}
$$
### Which features exist?
1) Numerical $x_{j} \in \mathbf{R}$ 
2) Categorical $x_{j} \in \{ c_{1}, \dots  c_{m} \}$
3) Ordinal $x_{j} \in \{ c_{1},\dots c_{m} \}$   (there is an $<$ operation) (there is no arithmetics)


### Type of ML task is defined by $\mathbf{Y}$
1) Supervised learning
	1) $\mathbf{Y} \in{R}$ (Regression)
	2) $\mid \mathbf{Y}\mid \;< \;\infty$ (Classification)
		- $\mathbf{Y} = \{ 0,1 \}$ - Binary Classification
		- $\mathbf{Y} = \{ 1, \dots, K \}$
		- $\mathbf{Y} = \{ 0,1 \}^K$ classification with intersecting classes multi lab
2) Unsupervised learning
	1) Clusterization 
		- X has to be split by groups so in every group objects will be similar
	2) Density estimation

3) Semi-Supervised learning (Частичное обучение)
	1) For some objects we know target, but for some we do not know.

4) Reinforcement learning 

### Formalization of ML Process
#### Class of models
$$
\mathbf{A} = \{ a(x,w)|w \} 
$$

$$
\begin{split}
L: \mathbf{Y} \times \mathbf{Y} \to \mathbf{R} \\
L(y, t) \\
\end{split}
$$
$y$ - correct answer, $t$ - predicted answer

#### Функционал ошибки / loss function
$$
\mathbf{Q}(a,X) 
$$

In majority of cases:
$$
Q(a, X) = \frac{1}{\ell}\sum_{i=1}^{\ell}L(y_{i}, a(x_{i}))
$$
Model training:
$$
\mathbf{Q}(a,X) \to \min\limits_{a \in \mathbf{A}}
$$
### Steps in task solving
1) Task formulation
2) Collect data
3) Feature engineering
4) Choice of loss function
5) Choice of models class
6) Model training
7) Model Validation
9) Production (MLops)
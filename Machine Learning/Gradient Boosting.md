([[Gradient Descent|Gradient]] boosting machine, GBM)

Key ideas:
- Let's train models iteratively, so that EVERY next model CORRECTS errors of PREVIOUS models.
- We calculate derivative of loss function for every observation from training data, then we minimize [[Ordinary Least Squares (OLS)|OLS]] for new sub-model and required shifts provided by derrivatives.
- If base models are too simple, quality of each base model would be bad, then it can ruin the ensemble.

### Boosting for [[MSE]]
$$
\begin{align}
&\frac{1}{l}\sum_{i=1}^{l}\left( a(x_{i})-y_{i} \right)^{2} \to \min_{a} \\
&a_{N}(x) = \sum_{n=1}^{N}\gamma_{n}b_{n}(x), \quad \gamma_{n}\, \in \,\mathbb{R} \quad \quad  b_{n}\text{ - model n}\\
&b_{1}(x): \quad  \frac{1}{l}\sum_{n=1}^{N}\left( b_{1}(x_{i}) - y_{i} \right) ^{2} \to \min_{b_{1}(x)} \mid b_{1}(x) \text{fix for next steps} \\
&b_{2}(x): \quad  b_{1}(x_{i}) + b_{2}(x_{i}) =y_{i} \\
&b_{2}(x_{i}) = y_{i}-b_{1}(x_{i}) = s_{i} \quad U \, \in \,R \implies \\
&\frac{1}{l}\sum_{i=1}^{l}\left( b_{2}(x_{i})-s_{i} \right) ^{2} \to \min_{_{b_{1}}}  \\
&\gamma_{2} = arg\min_{\gamma \, \in \, \mathbb{R}} \frac{1}{l} \sum_{i=1}^{l}\left( b_{1}(x_{i})+ \gamma b_{2}(x_{i})-y_{i} \right)^{2}   \\
&b_{3}(x): \quad s_{i}=y_{i}-b_{1}(x_{i}) - \gamma_{2}b_{2}(x_{i}) \\
&\frac{1}{l}\sum\left( b_{3}(x_{i})-s_{i} \right) ^{2} \to \min 
\end{align}
$$

When to stop?
- GB is overfitting
- Has to be examined with validation data
![[Pasted image 20231201112231.png]]


### General Case
$$
\begin{align}
&L(y,z) - \text{diff. loss function } \\
&a_{N}(x)=\sum_{i=n}^{N}\cancel{ \gamma_{n} } b_{n}(x) \quad  \text{For now we don't need } \gamma \\ \\
&\text{How to train?} \\
&b_{N}(x): \quad \underbrace{ \frac{1}{l}\sum_{i=1}^{l}L(y_{i}-a_{N-1}(x_{i}), \;b_{N}(x_{i})) }_{ \text{Bad}! } \\ \\
&\text{What's better?} \\
&b_{1}(x) - \text{train by any method} \\
&b_{N}(x): \quad b_{1}(x),\dots,b_{N-1}(x) - \text{ assume that already exist and fixed} \\
&\frac{1}{l}\sum_{i=1}^{l}L(y_{i}, \; a_{N-1}(x_{i})+b_{N}(x_{i}))\to \min_{b_{N}} \quad  x_{i}-\text{individual object.} \\
&\text{How can we optimize this loss?}
\end{align}
$$
![[Pasted image 20231128002020.png]]

Therefore:
$$
\begin{align}
&\text{Gradient Boosting:} \\
&s_{i}= -\frac{ \partial  }{ \partial z } L(y_{i},z) \mid_{z=a_{N-1}(x_{i})} \;\;  -\;\;\text{ shift (how to change prediction of)}
  \\
&\frac{1}{l}\sum_{i=1}^{l}\left( b_{N}(x_{i})-s_{i} \right) ^{2} \to \min_{b_{N}} \\
&a_{N}(x) = a_{N-1}(x) + b_{N}(x) \\ \\ \\

&\text{Why is it called Gradient Boosting:} \\
&Q(z_{1},\dots z_{l}) = \frac{1}{l}\sum_{i=1}^{l}L(y_{i},\; a_{N-1}(x_{i})+z_{i}) \quad  \text{for }  l\text{ objects}\\
&(s_{1},\dots,s_{l}) = \nabla_{z}Q(z)
\end{align}

$$

## Example
$$
\begin{align}
X = ((x_{1},y_{1}), (x_{2},y_{2})) \\
\frac{1}{2}\left( L(y_{1},z_{1}) + L(y_{2},z_{2})  \right ) \to \min_{} \\
\text{gradient of that by } z=(z_{1},z_{2}): \quad  s = (s_{1},s_{2}) 
\end{align}
$$
![[Pasted image 20231201113501.png]]

Gradient Boosting - [[Gradient Descent]] in space ensemble's prediction on training sample.

Difference with [[Gradient Descent]] is that we count anti-gradient, then we approximate this on training sample, in [[Gradient Descent]] we just adjust parameters of a model directly.

## Mysteries of GB (Control Work)
1) Why you can't think?
$$
\begin{align}
b_{1}(x) - \text{some model} \\
a_{N}(x_{i})= a_{N-1}(x_{i})+s_{i}
\end{align}
$$
We do not change predictions on objects  $x \, \cancel{ \in \, }X$
2) Why $b_{N}$ is trained on MSE
will be on seminar

## Loss Functions
#### Regression
$$
\begin{align}
L (y,z) = (y-z)^{2} \\
s_{i} = - \frac{\delta L}{\delta z}(y_{i}, z) \mid_{z=a_{N-1}(k_{i})} = y_{i} - a_{N-1}(x_{i})
 \\
L(y,z)=\mid y-z\mid \\
s_{i} = -sign(a_{N-1}(x_{i})-y_{i}) \\
\end{align}
$$

#### Classification
$$
\begin{align}
a_{N}(x) \, \in \, \mathbb{R} - \text{ Cerainty in positive class} \\
sign \quad a_{N}(x) \text{ - final prediction} \\
L(y,z) = \log(1+\exp(-yz)) \\
\frac{1}{l}\sum_{i=1}^{l}\left( b_{N}(x_{i}) -\underbrace{  \frac{y_{i}}{1+\exp(y_{i}a_{N-1}(x_{i}))} }_{ s_{i} = w_{i}y_{i} } \right)^{2} \to \min_{b_{N}} \\ \\
y_{i}a_{N-1}(x_{i}) \gg 0 \implies w_{i} \approx 0, s_{i} \approx 0 \implies \text{we dont touch such objects} \\
\underbrace{ y_{i}a_{N-1}(x_{i})\ll 0 }_{ outlier } \implies w_{i} \approx1, s_{i} \approx y_{i} \implies \text{trying to correct to right answer} \\
y_{i}a_{N-1}(x_{i}) \approx 0 \implies w_{i} = \frac{1}{2}, s_{i} = \frac{1}{2}y_{i} \implies \text{try to correct, but more moderately}

\end{align}
$$

We used here [[Logistic Regression|Logistic Loss Function]] and it is stable to outliers. 
$L(y,z)=e^{-yz}$ - [[Exponential Loss Function]] is not so stable, weights would lead to infinity. So for classification specific loss functions, can be unstable. 

## Boosting and Extrapolation
$b_{0}(x)$ - linear model (for extrapolation) 
$a_{N}(x)$ - is trained using boosting on $y_{i}-b_{0}(x)$

## Regularization
Can be experimentally proven, that in Boosting:
![[Pasted image 20231201114711.png]]

$\implies$ base models in GBM should be - not deep trees.

Problems:
- If base models will be too complex, there is a risk of instant over-fitting. 
$\implies b_{N}(x)$ .... you can not trust this guy

Step Reduction (Learning Rate):
$$
\begin{align}
a_{N}(x)= a_{N-1}(x) + \eta b_{N}(x) \\
\eta \, \in \,\left[ 0,1  \right] - \text{hyper-parameters} \\
\text{the bigger } \eta \text{ the bigger will be optimal } N 
\end{align}
$$
#### [[Decision Tree]] based GB regularization 
$$
b(x) = \sum_{i=1}^{\gamma}b_{j}\left[ x \, \in \,R_{j} \right] 
$$
([[Decision Tree#Analytic Form|Analytic form of a Decision Tree]])

Complexity indicators of a tree: 
1) $\gamma$ - number of leaves
2) $\lvert\lvert b \rvert\rvert = \sum_{i=1}^{\gamma}b_{j}^{2}$    -    the bigger this, the bigger chances of forced change of composition.
###### Optimization Goal With Regularization
$$
\begin{align}
\sum_{i=1}^{l}\left( -s_{i}b_{N}(x_{i}) + \frac{1}{2}h_{i}b_{N}^{2} (x_{i}) \right) + \alpha \gamma + \frac{\lambda}{2}\sum_{i=1}^{\gamma}b_{j}^{2} \to \min_{b_{N}(x)} 
\end{align}
$$
Let structure of a tree be fixed. What will be equal to predictions in leaves. 
$$
\begin{align}
&= \sum_{j=1}^{\gamma}\sum_{(x_{i}, y_{i})\, \in \,R_{j}} \left( -s_{i}b_{j}+\frac{1}{2}h_{i}b_{j}^{2} \right) + \alpha \sum_{i=1}^{\gamma}1 + \frac{\lambda}{2}\sum b_{j}^{2} = \\
&= \sum_{j=1}^{\gamma}\left( b_{j}\underbrace{ \left( -\sum_{(x_{i}, y_{i})\, \in \,R_{j}} s_{i}\right) }_{ =-s_{i} } +\frac{1}{2}b_{j}^{2}\underbrace{ \left( \sum_{(x_{i}, y_{i})\, \in \,R_{j}}h_{i} \right) }_{ =-H_{j} } + \alpha+\frac{\lambda}{2}b_{j}^{2}  \right)  =  \\
&= \sum_{j=1}^{\gamma}\underbrace{ \left( -s_{j}b_{j} + \frac{1}{2}\left( H_{j}+\lambda \right) b_{j}^{2} + \alpha  \right) }_{ \text{square polynomial in terms of } b_{j} } \\
&\text{Substitute }b^{*}_{j} = \frac{s_{i}}{H_{j}+\lambda} \\
&\underbrace{ = -\frac{\frac{1}{2}\sum_{j=1}^{\gamma}s_{i}^{2}}{H_{j}+\lambda} + \alpha\gamma = H(B) }_{ \text{Loss function for a tree given optimal predictions in leaves} }
\end{align}

$$
$R_{j}$ - $j$-th leaf 

![[Pasted image 20231216142428.png]]
We can use $H(b)$ as [[Impurity]]. 
$$
\begin{align}
Q(R,j,t) = H(R)- H(R_{l})- H(R_{r})
\end{align}
$$


## Implementations:
[[XGBoost]]
[[LightGBM]]
[[CatBoost]]

## Miscellaneous 
#### Weighting 
In classification task almost always:
$L(y,z) = \tilde{L}(yz)$
Then: $s_{i} = y_{i}\underbrace{ \left( -{\frac{ \tilde{\partial}L }{ \partial m }(m)} \mid_{m = y_{ia_{N-1}(x_{i})}} \right) }_{ w_{i} }$
#### Outliers

## Related
[[Gradient boosting over trees (GBDT)]]
[[Stochastic Gradient Boosting]]
[[Second Order Boosting]]
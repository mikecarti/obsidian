([[Gradient Descent|Gradient]] boosting machine, GBM)

Let's train models iteratively, so that EVERY next model CORRECTS errors of PREVIOUS models.

### Boosting for [[MSE]]
$$
\begin{align}
&\frac{1}{l}\sum_{i=1}^{l}\left( a(x_{i})-y_{i} \right)^{2} \to \min_{a} \\
&a_{N}(x) = \sum_{n=1}^{N}\gamma_{n}b_{n}(x), \quad \gamma_{n}\, \in \,\mathbb{R} \\
&b_{1}(x): \quad  \frac{1}{l}\sum_{n=1}^{N}\left( b_{1}(x_{i}) - y_{i} \right) ^{2} \to \min_{b_{1}(x)} \mid b_{1}(x) \text{fix for next steps} \\
&b_{2}(x): \quad  b_{1}(x_{i}) + b_{2}(x_{i}) =y_{i} \\
&b_{2}(x_{i}) = y_{i}-b_{1}(x_{i}) = s_{i}U \, \in \,R \implies \\
&\frac{1}{l}\sum_{i=1}^{l}\left( b_{2}(x_{i})-s_{i} \right) ^{2} \to \min_{_{b_{1}}}  \\
&\gamma_{2} = arg\min_{\gamma \, \in \, \mathbb{R}} \frac{1}{l} \sum_{i=1}^{l}\left( b_{1}(x_{i})+ \gamma b_{2}(x_{i})-y_{i} \right)^{2}   \\
&b_{3}(x): \quad s_{i}=y_{i}-b_{1}(x_{i}) - \gamma_{2}b_{2}(x_{i}) \\
&\frac{1}{l}\sum\left( b_{3}(x_{i})-s_{i} \right) ^{2} \to \min 
\end{align}
$$

When to stop?
- GB is overfitting
- Has to be examined with validation data
![[Pasted image 20231128001144.png]]


### General Case
$$
\begin{align}
&L(y,z) - \text{diff. loss function } \\
&a_{N}(x)=\sum_{i=n}^{N}\cancel{ \gamma_{n} } b_{n}(x) \quad  \text{For now we don't need } \gamma \\ \\
&\text{How to train?} \\
&b_{N}(x): \quad \underbrace{ \frac{1}{l}\sum_{i=1}^{l}L(y_{i}-a_{N-1}(x_{i}), \;b_{N}(x_{i})) }_{ \text{Bad}! } \\ \\
&\text{What's better?} \\
&b_{1}(x) - \text{train how we can} \\
&b_{N}(x): \quad b_{1}(x),\dots,b_{N-1}(x) - \text{ assume that already exist and fixed} \\
&\frac{1}{l}\sum_{i=1}^{l}L(y_{i}, \; a_{N-1}(x_{i})+b_{N}(x_{i}))\to \min_{b_{N}} \quad  \text{  How can we optimize it?}
\end{align}
$$
![[Pasted image 20231128002020.png]]

Therefore:
$$
\begin{align}
&\text{Gradient Boosting:} \\
&s_{i}= -\frac{ \partial  }{ \partial z } L(y_{i},z) \mid_{z=a_{N-1}(x_{i})} \;\;  -\;\;\text{ shift}
  \\
&\frac{1}{l}\sum_{i=1}^{l}\left( b_{N}(x_{i})-s_{i} \right) ^{2} \to \min_{b_{N}} \\
&a_{N}(x) = a_{N-1}(x) + b_{N}(x) \\ \\ \\

&\text{Why is it called Gradient Boosting:} \\
&Q(z_{1},\dots z_{l}) = \frac{1}{l}\sum_{i=1}^{l}L(y_{i},\; a_{N-1}(x_{i})+z_{i}) \quad  \text{for }  l\text{ objects}\\
&(s_{1},\dots,s_{l}) = \nabla_{z}Q(z)
\end{align}

$$


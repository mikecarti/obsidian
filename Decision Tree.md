### Motivation
[[Linear Regression|Linear models]] are very good as they are differential ([[Gradient Descent|GD]] can be applied).
But they are linear (that problem is solved in [[Deep Learning]]).

But not all problems in the world about differentiating. Example:
List Sorting
$$
(x_{1}, \dots, x_{n}) \underbrace{ \to }_{ a } (\tilde{x}_{1}, \dots \tilde{x}_{n}) \text{ - non-diff. task}
$$
So Decision Tree-like algorithms are really helpful in such cases.

### Definition
Decision tree - binary tree, where:
	1) $v$ - node with child nodes $\implies \beta_{v}:\mathbb{X}\to \{ 0,1 \}$ predicate
	2) $v$ - leaf $\implies c_{v} \, \in \, \mathbb{Y}$ - prediction.

## Structure
### Predicates
$$
\beta_{v}(x)=\left[ x_{j}\geq t \right] \text{ - we will use that one}
$$
$$
\begin{align} 
&\text{There are also these, not so popular} \\
&\beta_{v}(x)=\left[ \left< w,x \right> \geq t \right]   \\
&\beta_{v}(x)= \left[ \rho(x,x_{0})\geq t \right] 
\end{align}
$$
![[Pasted image 20231110114957.png]]
![[Pasted image 20231110115024.png]]

Every leaf is for every sub-plane.


##### Real Tree Example
![[Pasted image 20231110115118.png]]

Interesting, that [[Random Forest]]s and [[XGBoost]]-like algorithms also cut linearly.

### Different types of predicting
- Regression $\implies C_{v} \, \in \,\mathbb{R}$
- Classification $\implies C_{v} \, \in \, \{ 1,\dots,k \}$
$C_{v}\, \in \,R^{k}: \quad C_{v_{k}}\geq 0 \quad \sum_{C_{v}}=1$

## Training
Lemma: If in X there is no $x_{i}=x_{j}, y_{i}\neq y_{j}$ 
then there exists a tree with 0 error on training data.

Hypothesis: If from all correct trees from training data, take the smallest (in terms of nodes, depth, ...) then it won't [[Over-fitting|over-fit]]. (But that is an [[P vs NP|NP-hard]]  task. )
Then we should use greedy solutuion.

### Greedy Algorithm for training
Split Node$(m, R_{m})$ 
$m$ - number of vertice 
$R_{m}$ - objects from X that got into a current node

If stopping criteria is met:
$$
c_{m} = \begin{cases}
\text{average}  & R_{m}  & (\text{Regression}) \\
\text{the most frequent class}   &  & (\text{Multi-Class})\\
\text{Rate of classes in}  & R_{m}  & (\text{Multi-Class with probas})
\end{cases}
$$

output:
$$
j,t = arg\, \max_{j=1,\dots,d; \, t \, \in \,R}\underbrace{ Q(R_{m},j,t) }_{ \text{ loss function of predicate} }
$$
j - number of feature
t - threshold

loss function is also called *Критерий Информативности Предиката*

$$
\begin{align}
&R_{l} = \{ (x,y)\, \in \,R_{m}\mid \left[ x_{j} <t\right] =1 \} \\
&R_{r}= \{ (x,y)\, \in \,R_{m}\mid \left[ x_{j} \geq t\right] =1 \}  \\
&\text{SplitNode}(l, R_{l}) \\
&\text{SplitNode}(r, R_{r})
\end{align}
$$

### Stopping Criteria:
- Max depth
- Max number of objects in a leaf
- Error Rate in a leaf
- ...

### Quality Criteria of a predicate
$$
\begin{align}
H(R) - \text{impurity}
\end{align}
$$
Shows non-homogeneity of data in $R$ 

Examples:
- Regression $\implies H(R)= \frac{1}{\mid R_{m}\mid}\sum_{(x_{i},y_{i})\, \in \,R}\left( y_{i}-\bar{y}_{m} \right)^{2}$ - Sample Variance
- Classification $\implies p_{k}=\frac{1}{\mid R\mid}\sum_{x_{i},y_{i} \, \in \,R}\left[ y_{i}=k \right]$
$H(R)=-\sum_{k=1}^{K}(p_{k}\log p_{k})$ - [[Entropy (information theory)]] 

#### Common approach to building H(R):
$$
\begin{align}
&H(R) = \min_{c\, \in \,\mathbb{Y}}\frac{1}{\mid R\mid} \sum_{(x_{i},y_{i})\, \in \,R} L(y_{i},c) \\
&H(R) \text{ - error of best constant prediction} \\
&\text{If a constant can reach low error} \implies \text{ impurity is low}
\end{align}
$$
### Loss Function
$$
\begin{align}
Q(R_{m},j,t) = H(R_{m}) - \frac{{\mid R_{l}\mid}}{\mid R_{m}\mid }H(R_{l}) - \frac{{\mid R_{r}\mid }}{\mid R_{m}\mid}H(R_{r}) \to \max_{}
\end{align}
$$
$\frac{{\mid R_{l}\mid}}{\mid R_{m}\mid } \text{ and } \frac{{\mid R_{r}\mid}}{\mid R_{m}\mid }$ are needed to divide tree in most balanced way

For simplicity:
$$
\frac{{\mid R_{l}\mid}}{\mid R_{m}\mid }H(R_{l}) + \frac{{\mid R_{r}\mid }}{\mid R_{m}\mid}H(R_{r}) \to \min_{j,t}
$$

### Tree Pruning
cost-complexity pruning. (Cutting of nodes)

### [[Multi-Way Trees]]
Non-binary trees, but that's very hard to make, and there are over-fitting risks
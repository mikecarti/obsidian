Does not have anything common with [[Variance]].

## Intuition
$X$ - random variable. 
$\sigma(x) =$ the list of all events that can be stated in terms of $X$

## Definition for a sigma algebra gen. by $X$
The *smallest* list that satisfies:
1) $\forall t \in \mathbb{R}$    $\{ X \leq t \} \in \sigma(X)$  (we can compare $X$ with any real. num)
2) if  $A \in \sigma(X)$ then  $A^{C}\in\sigma(X)$      $\bar{A}=A^{C}$ - compliment
3) If  $A_{1} \in \sigma(X), A_{2} \in \sigma(X), \dots$ then $\cup_{i=1}^{\infty}A_{i}\in\sigma(X)$

## Definition in General
$\mathcal{F}$ is a $\sigma$-algebra IF
1) $\emptyset \in \mathcal{F}$
2) if $A\in \mathcal{F} \implies A^{C} \in \mathcal{F}$
3) If $A_{1},A_{2},A_{3},\dots\in \mathcal{F} \implies \cup_{i=1}^{\infty}A_{i}\in\mathcal{F}$

## Operations
+: $A \Delta B = (A/B)\cup(B/A)$
$\cdot$ : $A\cap  B$

### Independence to a Random Variable
Random variable $X$ is independent of $\sigma$ - algebra $\mathcal{F}$. 
$$
X \to \underbrace{ \sigma(X) }_{ \text{list of all possibly stated events} }
$$
## Conditional Expectation
$$
E(Y | \mathcal{F}) = R \text{ - random var. that satisfies req-ts.}
$$
1) $\sigma(R) \, \in \,\mathcal{F}$      (you can calculate R using info in $\mathcal{F}$)
2) the prediction error $Y-R$ is uncorrelated of any R.V. you can calculate using info in $\mathcal{F}$
 $Cov(Y-R, I_{A}) = 0$ for  $A\, \in \,\mathcal{F}$
3) $E(Y-R)= 0$
## Examples of Discrete Case.
1) [[Classwork (Stochastic Processes)|Classwork (Stochastic Processes)]] - 13.10

2) ![[Pasted image 20231013173211.png]]
3) [[Classwork (Stochastic Processes)#17.10 Seminar]] - 17.10

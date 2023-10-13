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

## Examples of Discrete Case.
[[Stochastic Processes/Classwork|Classwork]] - 13.10

![[Pasted image 20231013173211.png]]

2 guys go to the work by bus.

A : waits for the 1st bus.
B : waits for the 2nd bus. 

THEN second bus will have FEWER people.

![[Pasted image 20230922172810.png]]


### Which bus will be more crowded? And by how much~ ?
Given all [[Poisson Distribution#Assumptions|5 Assumptions of Poisson]] distribution.

Number of people in a bus ($T_{i}$) is ~ proportional to wait between buses.
$$
E(T_{R}) \qquad\qquad E(T_{R+1})
$$
$R$ - random number of the first bus you will see
$\mathbb{E}(T_{1})=\mathbb{E}(T_{2})=\dots=\mathbb{E}(T_{R})$ (by the [[Poisson Distribution#Assumptions|theorem]])

![[Pasted image 20230922173443.png]]

$$
\mathbb{E}(T_{R})>\mathbb{E}(T_{R+1})
$$

These are independent:
![[Pasted image 20230922173740.png |400]]

$$
\begin{align}
T_{2}\sim T_{1}\sim T_{1}&\sim T_{2}\sim \dots\sim Exp(\lambda) \\
\mathbb{E}(T_{1})&=\frac{1}{\lambda} \\
\mathbb{E}(T_{R})&=\frac{1}{\lambda}+\frac{1}{\lambda}=\frac{2}{\lambda} \\
\mathbb{E}(T_{R})&=2 \cdot E(T_{R+1}) \\
\mathbb{E}(T_{R+1})&=\frac{1}{\lambda}
\end{align}
$$



# 07.09
## Tasks:
![[Pasted image 20230905150123.png]]

$$
{1} - \text{sleeping} \;\;\;\;\;\
{2} - \text{studying}
$$
a)
$$
\begin{bmatrix}
p_{1,1} & p_{1,2} \\
p_{2,1} & p_{2,2}
\end{bmatrix} = \begin{bmatrix}
0.25 & 0.75 \\
0.5 & 0.5
\end{bmatrix}
$$
$P^n - \text{got to some state in n steps}$

c) 
$P^1[p_{1} \to p_{2}] = P^1[p_{1,2}] = 0.75$
$P^2[p_{1,2}] = p_{1,1,2} \lor p_{1,2,2} = 0.25  \cdot 0.75  + 0.75  \cdot 0.5 = 0.5625$

d)
P(sleeps) = P(1) = 2/3
$$
[P[p_{1}], P[p_{2}]] =  \left( \frac{2}{3}, \frac{1}{3} \right) \cdot  \begin{bmatrix}
0.25 & 0.75 \\
0.5 & 0.5
\end{bmatrix}
$$




![[Pasted image 20230905152521.png]]

a)
![[Markov chain 2023-09-05 15.22.37.excalidraw| 200]]

b) 
china - 1
russia - 2
UAE - 3
$$
\begin{bmatrix}
p_{11} & p_{12} & p_{13} \\
p_{21} & p_{22} & p_{23} \\
p_{31} & p_{32} & p_{33} 
\end{bmatrix} = 
\begin{bmatrix}
0 & 0.75 & 0.25  \\
0 & 0.75 & 0.25 \\
0 & 0.25 & 0.75
\end{bmatrix}
$$
с) $P^1[{p_2}], P^2[{p_2}]\;-\;?$

[[First Step Analysis]]
![[Pasted image 20230905155207.png]]

a) ![[Markov chain 2023-09-05 15.52.27.excalidraw]]
# 12.09
[[First Step Analysis#Example]]

Task 5
![[Pasted image 20230912151955.png]]


b) Bob is more probable
![[Drawing 2023-09-12 15.20.49.excalidraw]]

c) 
$P_{17} = 0.5P_{27} + 0.5P_{37}$
$P_{37} = 0.5 \cdot P_{57} + 0.5 \cdot P_{27}$
$P_{57}= 0.5 + 0.5 \cdot P_{77}$
$P_{27} = 0$

Calculations ...

d) 
$P_{\\text{fin. in 4}} = \frac{\text{N finish in 4}}{\text{N toss = 5 combinations}}$
![[Pasted image 20230912155522.png | 500]]


$\text{N("finish in 4")} = 3$


# 15.09 Lecture

#### № 1.6
![[Pasted image 20230915162525.png]]


![[Pasted image 20230915162634.png]]

$T$ - first moment of time when $X_{T} = 0$
Start: $X_{0} = 1$

Problem: Calculate P(T=k) $\forall k$
$$
\begin{align}
P(T=0)=0 \\
P(T=1)=\frac{1}{2} \\
P(T=2)=0 \\
P(T=3)= \frac{1}{2} \cdot \frac{1}{2} = \frac{1}{8} \\
P(T=123) = \text{hard :)}
\end{align}
$$
$$
\begin{align}
g(u)&=p_{0} \cdot 1 + p_{1} \cdot u+p_{2} \cdot u^2+p_{3} \cdot u^3+\dots \\
\text{if  } g(u) &= 0 + \frac{1}{2}u^1 + 0 \cdot u^2 + \frac{1}{8} \cdot u^3 + \dots
\end{align}
$$
where $u$ - argument of a function (way to pack all probabilities in 1 func.)
![[Pasted image 20230915163912.png|500]]

$$
E(u^T)=p_{0} \cdot u^0+p_{1} \cdot u^1 + p_{2} \cdot u^2
$$
Calculate only one function $E(u^T) \implies$ 
$\implies$Extract all probabilities.

Divide paths into segments:
![[Pasted image 20230915164551.png |400]]

**$T_{1}, T_{2}$ are independent
$T_{1},T_{2},T$ identically distributed**

![[Pasted image 20230915165416.png]]
*Replacing $T$ with $1 +T_{1}+T_{2}$*

Powerful ideas for this task:
- [[Probability Generating Function]]
- [[First Step Analysis]]
$$
\begin{align}
E(u^T) &=\frac{1}{2}u^1+\frac{1}{2}E(u^{1+T_{1}+T_{2}}) \\
E(u^T) &=\frac{1}{2}u^1+\frac{1}{2}E(u) \cdot E(u^{T_{1}}) \cdot E(u^{T_{2}})  \\
g(u)&=\frac{1}{2} \cdot u+ \frac{1}{2} \cdot u \cdot g(u)  \cdot g(u) \\
u^2g^2&-2gu+1-1+u=0 \\
(ug-1)^2&=1-u^2 \\
ug-1&=\pm \sqrt{ 1-u^2 } \\
g(u)&={ \frac{1\pm\sqrt{ 1-u^2 }}{u}} \\
(t+1)^{\alpha} &= 1 + C^1_{n}+C^2_{n}+C^3_{n} \cdot t^3 +\dots \;\;\;\ t = -u^2 \\ 
g(u)&=\frac{{1\pm(1-u^2)^{1/2}}}{u} \;\;\;\; \text{choosing}  \; - \\ 
\text{by having   } t &= -u^2 \text{ and having this taylor expansion} \\
&\text{we can transform this to binomial form} \\
g(u)&=C^1_{0.5}u - C^2_{0.5}u^3 + C^3_{0.5}u^5 + \dots\\ 
C^3_{5} = \frac{5!}{3!2!} &\equiv C^k_{\alpha}= \frac{\alpha(\alpha-1)\dots(\alpha-l+1)}{k!} \implies\\
C^3_{0.5} &= \frac{{0.5 \cdot (0.5-1) \cdot (0.5-2)}}{3!} \\ \\

P(T=7) = -C^4_{0.5} &= \frac{{-0.5(-0.5-1) \cdot (0.5-2)(0.5-3)}}{4!} \\
P(T=2n-1) &= \begin{cases}
0 & \text{if k is even} \\
\frac{(2n-2) \cdot (2n-4) \cdot \dots 1}{2^n \cdot n!} & \text{if k is odd}
\end{cases}
\end{align}
$$


№ 2.4
$x \in \{ 0,1,2,3,4,\dots \}$
$g(u) = E(u^x)=0.1+0.2u+0.15 \cdot u^2 + \dots$
$P(X=0)=0.1$
$P(X=1)=0.2$
$P(X=2)=0.15$
$P(X=3) \in [0; 0.55]$


№ 2.3
$$
MGF = E(\exp(tu))= 1+2t+7t^2+20t^3 + \dots
$$
$E(u)=M'(0) = [2+7 \cdot_{2} \cdot t + 20 \cdot_{3} \cdot t^2]_{t=0}=2$ 
$E(u^2) =M''(0) = 7 \cdot 2=14$
$E(u^3) =M'''(0) = 20 \cdot 2 \cdot 3 \cdot 1 = 120$
$Var(u)=14-2^2=10$
$$
MGF(t)=1+k_{1} \cdot t+k_{2} \cdot t^2 + \dots
$$
$$
E(u^n)=k_{n} \cdot n!
$$

# 19.09 Seminar


![[Pasted image 20230919152104.png|600]]
$\pi_{1}$ is a stationary [[Markov chain]]

$N$ - number of times we visit points
$N_{i}$ - number of times we've been in point $i$
$$
\begin{bmatrix}
\pi_{1} \\
\pi_{2} \\
\pi_{3} \\
\end{bmatrix} - \text{stationary distribution}
$$
China: $\pi_{1}=\frac{2}{3}\pi_{2}$ 
Russia: $\pi_{2}=\frac{3}{4}\pi_{1} +\frac{1}{2}\pi_{2} + \frac{1}{2}\pi_{3}$
UAE: $\pi_{3}=\frac{1}{4}\pi_{1}+\frac{1}{2}\pi_{3}$

Solutions:
$$
\begin{bmatrix}
\pi_{1} \\
\pi_{2} \\
\pi_{3}
\end{bmatrix} = \begin{bmatrix}
\frac{1}{3} \\
\frac{1}{2} \\
\frac{1}{6}
\end{bmatrix}
$$

if $\lim_{ n \to \infty }\mathbb{P}^N$
$$
\mathbb{R}_{stationary}=\begin{bmatrix}
\frac{1}{3} & \frac{1}{2} & \frac{1}{6} \\
\frac{1}{3} & \frac{1}{2} & \frac{1}{6} \\
\frac{1}{3} & \frac{1}{2} & \frac{1}{6}
\end{bmatrix}
$$


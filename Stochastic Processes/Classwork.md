
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



# 22.09 Lecture
Ex. 
$P(X_{1.002}-X_{1}=1)=0.01$
$P(X_{1.006}-X_{1}=1) \approx 0.03$

![[Pasted image 20230922171530.png]]

$$
\begin{align}
\mathbb{E}(X_{t+10})-X_{t} = 2 \\
X_{t+10}-X_{t}\sim Poiss(\lambda \cdot 10) \\
\mathbb{E}(X_{t+10}-X_{t})=10\lambda =2  \\
N_{k} \sim Exp(\lambda), T_{n+1} \sim Exp(\lambda) \\
P(T_{n+1}>7)=\exp(-\lambda \cdot 7)=  \\
= \exp\left( -\frac{1}{5} \cdot 7 \right) \approx 0.24
\end{align}
$$

Ex.![[Pasted image 20230922184610.png]]
Lena send messages to Masha according to [[Poisson Distribution| P.P (Poisson Process)]] ($\lambda_{L}=10 \frac{msg}{hour}$)
Alex send messages to Masha according to [[Poisson Distribution| P.P (Poisson Process)]] ($\lambda_{A}=2 \frac{msg}{hour}$)

$P(\text{"Masha will recieve exactly 15 msgs in next 40 minutes"})=?$

$\lambda_{total}=10+2=12 \text{ msg/hour}$
$$
\begin{align}
P(Z_{40}-Z_{0}=15)=P(Z_{40}=15)=\frac{\exp\left( -\frac{12}{60}40 \right)\left( \frac{12}{60}40 \right)^{15}}{15!}
\end{align}
$$
using [[Poisson Distribution#K occurrences in an interval]]

Ex.
![[Pasted image 20230922185706.png]]

$\lambda_{A}=5$ per minute
$\lambda_{B} = 2$ per minute

$P(T^{A}_{1} < T^{B}_{1}) = ?$
guess: $\frac{\lambda_{A}}{\lambda_{A}+\lambda_{B}}$

![[Pasted image 20230922190819.png]]


Ex. ![[Pasted image 20230922191313.png]]

a) $P(\text{"I will see exactly 2 taxis before bus"})=?$
b)$P(\text{"I will observe at least 2 taxis before bus"})=?$

$P(\text{"Observe taxi before a bus"})=\frac{5}{7}$
a) P = $\frac{5}{2+5} \cdot \frac{5}{2+5}  \cdot \frac{2}{2+5}$
b) P = $\frac{5}{2+5} \cdot \frac{5}{2+5}$

# 26.09 Seminar
![[Pasted image 20230926145631.png]]
![[Pasted image 20230926145639.png]]

![[Pasted image 20230926145414.png | 250]]
$105 \to 98$
#### Hint
- decomposition
- [[First Step Analysis]]

b)

c)
#### Decomposition
$$
\begin{align}
T_{105, 98} &= T_{105, 100} + T_{100, 98} \\
T_{105, 104} &= T_{104, 103} \\
T_{105, 100} &= 5  \cdot  T_{105, 104} \\
T_{105, 104} &= 1 + \frac{2}{3} \cdot 0 + \frac{1}{3}T_{102, 100}  = 1+ 0 + \frac{1}{3}  \cdot  2  \cdot  T_{105, 104} \implies\\
T_{101, 100} &= 1 + \frac{2}{3} \cdot  T_{101, 100} \implies \\
T_{101, 100} &= 3
\end{align}
$$


## Task 0
[[Weak Law of Large Numbers#Proof]]


## Task 4
![[Pasted image 20230926154646.png]]

$X_{n}\sim Exp(n)$

a) 
$$
\begin{align}

f_{n}(X) &= \begin{cases}
ne^{-nx} & x\geq 0 \\
0 & x<0
\end{cases}  \\
F_{X}(x) &= \begin{cases}
1 - e^{-nx} & x\geq 0 \\
0 & x<0
\end{cases} \\

\end{align}
$$
![[Pasted image 20230926155607.png | 450]]

b)
$$
\begin{align}
\lim_{ n \to \infty } \mathbb{P}(| X_{n}- 0| > \epsilon) &= 0 \\
\text{Proof:} \\
\lim_{ n \to \infty } \mathbb{P}(| X_{n}- 0| > \epsilon) &= \lim_{ n \to \infty } (X_{n}>\epsilon)  = \\
= 1 - \lim_{ n \to \infty } \mathbb{P}(X_{n}\leq\epsilon)&=1 - \lim_{ n \to \infty } F_{X}(x) =  \\
= 1 - \lim_{ n \to \infty } ( 1-e^{-n\epsilon}) &= \lim_{ n \to \infty } e^{-n\epsilon} = 0
\end{align}
$$


## 06.10 Lecture
![[Pasted image 20231006162703.png]]

a) warm-up P(you will answer correctly) = $0.7 + 0.3 \cdot \frac{1}{3} = 0.8$
b) N=3 (N is not random yet)
$P(\text{"You know just one quest. | you have answered 3 questions correctly"}) =$
$$
\begin{align}
\frac{{P(A\cap B)}}{P(B)}={\frac{P(\text{I know 1, answer 3 correctly})}{P(\text{I answer 3qs corr.})}} =  \\
= \frac{{C_{3}^{1} \cdot 0.7^{1} \cdot \left( 0.3 \cdot \frac{1}{3} \right)^{2}}}{\left( 0.7+0.3 \cdot \frac{1}{3} \right)} =
\end{align}
$$
c) i
$$
\begin{gather*}
f_{T}(t) = \begin{cases}
\alpha \exp(-\alpha t) & \text{if you know the answer} \\
5\alpha \cdot \exp(-5\alpha t) & \text{ if you guess}
\end{cases} \\
T_{1} \sim \exp(rate=\alpha) \\
T_{2}\sim \exp(rate=5\alpha) \\
T = I \cdot T_{1}+(1-I) \cdot T_{2}   \\
I \text{ - random variable} \\
A: I=1 \text{ or } I = 0 \\
P(A): 0.7 \text{ or } 0.3 \\ \\
E(T)=E(IT_{1}+(1-I)T_{2})=E(IT_{1})+E((1-I)T_{2})= \\
=E(I) \cdot E(T_{1})+ E(1-I) \cdot E(T_{2}) = \\
\end{gather*}
$$

c) ii
![[Pasted image 20231006164654.png]]

$$
\begin{align}
E(W)=E(E(W|N)) \quad \text{ law of total expected value} \\
\text{ Adam's law Tower property} \\
Var(W) = E(Var(W|N)) + Var(E(W|N)) \quad \text{ Evve's Law}
\end{align}
$$


![[Pasted image 20231006172744.png]]

![[Pasted image 20231006173303.png]]


### 13.10 Lecture

$Ex$.
$\sigma(Y), \sigma(X^{2}), \sigma(\mid X\mid \cdot Y)$ - ?
![[Pasted image 20231013164409.png]]

a) $\sigma(Y)$ = $\{ \{ Y=0 \}, \{ Y=1 \}, \Omega ,\emptyset\}$
$\Omega$ - the trivial event that always happens (universe for our experiment)
$\emptyset$ -  the trivial event that never happens (universe for our experiment)

b) $\sigma(X^{2})$    $\{X=-2\} \cancel{ \in } \sigma(X^{2})$
$\{  X^{2} = 4\} = \{ X=2 \}U\{ X=-2 \}$
$\{ X^{2}=25 \}= \{ X=5 \}$

$\sigma(X^{2}) = \{ \{ X^{2}=4 \}, \{ X^{2}=25 \}, \Omega, \emptyset \}$

c) $\sigma(|X| \cdot Y)$                           $|X| \cdot Y \in \{ 0,2,5 \}$ 

$\{ |X| \cdot Y>1 \}=\left\{  |X| \cdot Y> \frac{1}{2}  \right\} = \{ |X| \cdot Y=2 \text{ OR }5 \}$
$\{ |X| \cdot Y=0 \}=\{ \sin(|X| \cdot Y)\leq 0 \}=\{ \log(|X| \cdot Y+1)=0 \}$
$\sigma(|X| \cdot Y)=\{ \Omega, \emptyset, \{ |X| \cdot Y=2 \}, \{ |X| \cdot Y=5 \}, \{ |X| \cdot Y\neq 0 \}, \{ |X| \cdot Y\neq 2 \}, \{ |X| \cdot Y \neq 5\}\}$
d) How many events are there in $\sigma(X,Y)?$
$\{ X<Y \}$, $\{X^{2}>{Y^{2}}\}$ 
$\{ X^{2}+Y^{2}=5 \}=\{ |X|=2,Y=1 \}=\{ X<5,Y>0 \}$
$$
\begin{align}
\sigma(X,Y)=\{ \{ X=-2,Y=1 \}, \dots\dots, \{ X<5, Y>0 \} \}  \\
\text{3 X values, 2 Y values, so we have 6 outcomes} \\
\text{We can take emptyset, we can combine all outcomes } \Omega \\
\vdots \\
\text{in total Cardinality: } cord\left( \sigma(X,Y) \right) = 2^{6} = 64 \text{ elements} 

\end{align}
$$
2 - because we can take or not take, 6 because we have 6 cells.
![[Pasted image 20231013172126.png]]



### 17.10 Seminar
- Task 1 
Toss a dice: $\Omega$ = $\{ 1,2,3,4,5,6 \}$
$$
\begin{align}
\mathcal{F}_{1} &= \sigma(\text{we know that there was a toss}) = \{ \emptyset, \Omega \} \\
\mathcal{F}_{2} &= \sigma(\text{we saw a number on a dice}) = \underbrace{ \{\emptyset,  \Omega, \{ 1 \}, \dots, \{ 6 \}, \{ 1,2 \}, \dots \} }_{ \text{a partition (all smallest pieces)} } \\
A_{i} &\in \mathcal{F} \\
\Omega &= \cup_{i\in I}A_{i} \\
A_{i}&\cap A_{j} = \emptyset \\
\forall A &\in \mathcal{F} : \exists \mathcal{J}\subset I \; A=\cup_{i\in J}A_{i} \\ \\
\mathcal{F}_{3} &= \sigma(\text{1,2 or many}) =\{ \emptyset, \{1\}, \{ 2 \}, \{ >2 \}, \dots, \{ 1,2 \}, \{ 1,>2 \}, \dots, \Omega \}   \\
&\{ \emptyset, \underbrace{ \{ 1 \}, \{ 2 \}, \{ 3,4,5,6 \} }_{ partition }, ... \} \\
&cord(\mathcal{F}_{3}) = 2^{3}
\end{align}
$$


$$
\begin{align}
& \\
& \\
& \\
&
\end{align}
$$
# HW 1 stochastic process

# N1
a)

![[Drawing 2023-10-14 23.39.14.excalidraw|200]]

P(2 HEDGEHOGS WILL BE AT ONE POINT IN 3 STEPS) = P(Z)?

$$
\begin{align}
P(\text{same vertex in 1 step}) = 0 \\
P(\text{same vertex in 2 steps}) = ?  \\
\end{align}
$$
Such is only possible in $D$, and as they do 2 steps both formula can be written as:
$$
\begin{align}
P(\text{same vertex in 2 steps}) = \left( \frac{1}{2} \right)^{2} \cdot\left(  \frac{1}{2} \right)^{2} = \frac{1}{16}  \\
\end{align}
$$
As we already understood, the only direction in which distance is even, is direction counter-clocwise for A-hedgehog, and clockwise for B-hedgehog. Here are several examples:
![[2023-10-14 2023-10-15 00.36.34.excalidraw]]

It looks like to be in one vertice in 3 moves, they have to be either on E or C, because they can do only odd number of moves both. Then problem is to find 
$P(H1=H2=E\; or \;H1=H2=C)$

$$
\begin{align}

M^{Transition} = M = \begin{bmatrix}
! & A & B & C & D & E \\
A  & 0 & \frac{1}{2} & 0  & 0 & \frac{1}{2}\\
B  & \frac{1}{2} & 0 & \frac{1}{2} & 0 & 0\\
C  & 0 & \frac{1}{2} & 0 & \frac{1}{2} & 0\\
D  &0  & 0 & \frac{1}{2} & 0 & \frac{1}{2}\\
E & \frac{1}{2} & 0 & 0 & \frac{1}{2} & 0
\end{bmatrix} \\ \\

M^{3} = \begin{bmatrix}
! & A & B & C & D & E  \\
A  & 0& \frac{3}{8} & \frac{1}{8} & \frac{1}{8} & \frac{3}{8}  \\
B  & \frac{3}{8} & 0  & \frac{3}{8} & \frac{1}{8} & \frac{1}{8}\\
C  & \frac{1}{8} & \frac{3}{8} & 0 &  \frac{3}{8}& \frac{1}{8}\\
D   & \frac{1}{8} & \frac{1}{8} & \frac{3}{8} & 0  & \frac{3}{8}\\
E  & \frac{3}{8} & \frac{1}{8} & \frac{1}{8} & \frac{3}{8} & 0
\end{bmatrix}
\end{align}
$$

After 3 moves:
$$
\begin{align}
P(Z) = 0 \cdot \frac{3}{8} + \frac{3}{8} \cdot 0 + \frac{3}{64} + \frac{1}{64} + \frac{3}{64} = \frac{7}{64} = \frac{7}{2^{6}}
\end{align}
$$
Answer: $\frac{7}{64}$


b) 2nd attempt
S - Same Vertex
A - Adjacent
N - Non-Adjacent

$$
M_{b} = \begin{bmatrix}
! & S & A & N \\
S  & \frac{1}{2}  & 0 & \frac{1}{2}\\
A  & 0 & \frac{3}{4} & \frac{1}{4}\\
N  & \frac{1}{4} & \frac{1}{4} & \frac{1}{2}
\end{bmatrix}
$$

c) 
as $N \to \infty$
$$
\begin{gather}
\mathbb{R}_{b} = \pi = \pi M_{b} = \begin{bmatrix}
x & y & z
\end{bmatrix}\\
\begin{bmatrix}
x & y & z
\end{bmatrix} = \begin{bmatrix}
x & y & z
\end{bmatrix}  \cdot \begin{bmatrix}
 \frac{1}{2}  & 0 & \frac{1}{2}\\
 0 & \frac{3}{4} & \frac{1}{4}\\
 \frac{1}{4} & \frac{1}{4} & \frac{1}{2}
\end{bmatrix} =  \\
\begin{bmatrix}
\frac{x}{2}+\frac{z}{4} & \frac{3y}{4}+\frac{z}{4} & \frac{x}{2}+\frac{y}{4}+\frac{z}{2}
\end{bmatrix} \implies \\
\begin{cases}
4x = 2x + z \\
4y = 3y + z \\
4z = 2x + y + 2z 
\end{cases} \implies \\
x = \frac{z}{2} \\
y = z  \implies  \\
\begin{bmatrix}
x & y & z
\end{bmatrix} = \begin{bmatrix}
x & 2x & 2x 
\end{bmatrix} = \begin{bmatrix}
0.2 & 0.4 & 0.4
\end{bmatrix} \\
\text{as sum of elements sum up to 1}: x = \frac{1}{5} \\ \\

\end{gather}
$$

d) Find the expected time until the hedgehogs meet in one vertex
$$
\begin{align}
\mathbb{E}[X] = \mathbb{E}[\text{steps until hedgehogs are on same vertex}] =  \\
\end{align}
$$
Let us reframe the model. It is equivallent to only 1 hedgehog, that either moves 2 steps, or is staying where he is. With 1/4 proba. that he moves 2 steps right, 1/4 proba. that he moves 2 steps left, and 1/2 proba. that he will not move.

To meet other hedgehog, he needs to make two steps in direction of another hedgehog. So....
$$
\begin{gather}

M_{b} = \begin{bmatrix}
! & S & A & N \\
S  & \frac{1}{2}  & 0 & \frac{1}{2}\\
A  & 0 & \frac{3}{4} & \frac{1}{4}\\
N  & \frac{1}{4} & \frac{1}{4} & \frac{1}{2}
\end{bmatrix} \\
\begin{cases}
\mathbb{E}[X] = T_{AS} = 1 + \frac{3}{4} \cdot T_{AS} + \frac{1}{4} \cdot T_{NS} \\
T_{NS} = 1  + T_{AS} \cdot \frac{1}{4} + T_{NS}  \cdot  \frac{1}{2} \\
\end{cases} \\
\begin{cases}
4T_{AS}=4 + 3T_{AS}+T_{NS} \implies T_{AS} = 4 + T_{NS} \\
4T_{NS} = 4 + T_{AS} + 2T_{NS} \implies 2T_{NS} - 4 = T_{AS} \\
\end{cases} \\
4 + T_{NS} = 2T_{NS} -4  \\
T_{NS} = 8 \;\; T_{AS} = 12 \\
\text{Answer: } 12 \text{ steps} 
\end{gather}
$$


# N2
Each day the Random Restaurant is independently closed with probability p. If the restaurant is open then the number of clients has Poisson distribution with mean µ = $\lambda$.

After N days (working or non-working) the Random Restaurant will permanently close, N is random and has Poisson distribution with mean n.

(a) Find the moment generating function of the number of clients during day 1, assuming N $\geq$ 1.

$$
\begin{align}
&X \text{ - number of clients a day} \\
&X \sim Poisson(\mu)   \\
&\mu = \lambda  \\

&f(X=k) = {\displaystyle {\frac {\lambda ^{k}e^{-\lambda }}{k!}}} \\
&M_{pX}(t) = E(e^{(1-p)tX}) = \sum_{x}e^{t(1-p)x}f_{X}(x) = \sum_{x=0}^{\infty} \left(    e^{t(1-p)x}{\frac {\lambda ^{x}e^{-\lambda }}{x!}}\right)= \\
=& e^{-\lambda} \sum_{x=0}^{\infty} \left({\frac {e^{t(1-p)x}\lambda ^{x}}{x!}}\right) = e^{-\lambda} \sum_{x=0}^{\infty} \left(\frac{(e^{t(1-p)} \lambda)^{x}}{x!}\right) =  \\
=& e^{-\lambda} e^{e^{t(1-p)}\lambda} = e^{e^{t(1-p)}\lambda-\lambda}= e^{\lambda(e^{t(1-p)}-1)} = \underbrace{ \exp \left(   {\lambda(\exp(t(1-p))-1)} \right) }_{ MGF \text{ for N. of Clients Day 1} } \\ \\

&\mathbb{E}[X] = \frac{dM_{pX}(t)}{dt} = (1-p)\lambda \exp(0)= (1-p)\lambda \text{ - correct} 
\end{align}
$$

(b) Find the moment generating function of the total number of clients served in the Random Restaurant
$$
\begin{align}
&X - \text{ number of clients served a day} \sim Pois(\mu) \\
&Z  - \text{total number of clients in rest.}  \\
&B - \text{Restaraunt is open} \sim Bernoulli(1-p) \\
&Z = B_{1}X_{1} + \dots + B_{N}X_{N}\\
&E[Z] = (1-p)X  \cdot  E[N] = (1-p)X  \cdot  n  =  \\
&= P(\text{"rest. is open"}) \cdot  \text{"Number of clients a day"} \cdot  \text{"expected n. of days"}  \\
&M_{Z}(t) = M_{X}(t)
\end{align}

$$

$$
\begin{align}
&X - \text{ number of clients served a day} \sim Pois(\mu)  \\
&Z - \text{number of clients total} \\
&M_{Z | N}(t) = E[e^{Zt}\mid N] = E\left[  \exp \left(  (1-p)t(X_{1}+ \dots+X_{N}) \right)\mid N \right] =  \\
& E(\exp(tx_{1}(1-p))\mid N) + \dots + E(\exp(tx_{N}(1-p))\mid N) = \\
&= M_{Z | N}(t) = E(\exp ((1-p)Xt))^{N}  \\
&M_{Z}(t) = E[e^{Zt}] = E[E[e^{Zt}\mid N]\,] = E[]
\end{align}
$$




# N3
Find the probability limit $plim\; Xn$, where
$$
\begin{align}
&X_{n} = \frac{{Y_{1}+2Y_{2}+\dots+nY_{n}}}{n^{2}} \\
&Y_{k} \sim U(0,1) \\ \\

&\mathbb{E}[X_{n }] = \frac{E[Y_{1}] + 2E[Y_{2}] + \dots + nE[Y_{n}]}{n^{2}} =  \frac{E[Y](1 + 2 + \dots + n)}{n^{2}}  \\
&= \frac{{0.5 \cdot {\frac{n(n+1)}{2}}}}{n^{2}} = \frac{{0.25(n+1)}}{n} = \frac{{n+1}}{4n} \\
&\mathbb{Var}[X_{n}] = \text{using independence}= \frac{{var(Y_{1})+ \dots +var(nE[Y_{n}])}}{n^{4}} = \\
&var(Y) = {\displaystyle {\tfrac {1}{12}}(b-a)^{2}} = \frac{1}{12} \\
& = \frac{{\frac{1}{12} + 4 \cdot \frac{1}{12} + \dots + n^{2}  \cdot  \frac{1}{12}}}{n^{4}} = \frac{\frac{1}{12}(n(n+1)(2n+1))}{6n^{4}} \\
 &= \frac{(n(n+1)(2n+1))}{72n^{4}} \\
&\lim_{ n \to \infty } \mathbb{Var}[X_{n }] = \frac{n^{3}\dots}{n^{4}\dots} = 0  \\
&\text{ then } \lim_{ n \to \infty } E[X_n] = plim[X_n] \\
&\lim_{ n \to \infty } E[X_{n}] = \lim_{ n \to \infty } \frac{{n+1}}{4n} = \frac{1}{4} \\
&\text{Answer: } \frac{1}{4}

\end{align}
$$
# N4

Consider the Poisson arrival process $X_t$ with constant rate λ.
Now let’s scale the time in a non-linear fashion, $Y_t = X_{t^{2}}$
(a)
Find $\mathbb{E}[Y], \mathbb{V}[Y], \mathbb{P}(Y=0)$
$$
\begin{align}
&E[Y_{t}] = E[X_{t^{2}}] = \lambda t^{2} \\
&Var[Y_{t}] = Var[X_{t^{2}}] = \lambda t^{2} \\
&P(Y=0) = P(X_{t^{2}}=0) = e^{-\lambda t^{2}}
\end{align}
$$

(b) Find $E(Y_{t+5} | Y_t)$ and $Var(Y_{t+5} | Y_t)$.
$$
\begin{align}
&E(Y_{t+5}\mid Y_{t}) =  E(X_{(t+5)^{2}} | X_{t^{2}}) =E(X_{t^{2}+10t +25} | X_{t^{2}}) = \\
= & X_{t^{2}} + E(X_{10t + 25}) = X_{t^{2}} + \lambda(10t+25) \\ \\
&Var(Y_{t+5} \mid Y_{t}) =  E(X^{2}_{(t+5)^{2}} | X_{t^{2}}) -  E(X_{(t+5)^{2}} | X_{t^{2}})^{2} = \\
=& E(X_{(t+5)^{4}} | X_{t^{2}}) -  E(X_{(t+5)^{2}} | X_{t^{2}})^{2} = E(X_{625 + 500 t + 150 t^2 + 20 t^3 + t^4}|X_{t^{2}}) - \\
&( X_{t^{2}} + \lambda(10t+25))^{2} = X_{t^{2}} + \lambda((t+5)^{2}-t^{2}) - ( X_{t^{2}} + \lambda(10t+25))^{2}
\end{align}
$$


# N5
Let’s toss a dice until the first six appears. Let X be the result of the first toss and Y — the total number of tosses.

(a)
Find E(X | Y)
$$
\begin{align}
&\mathbb{E}[X|Y] = \mathbb{E}[\text{first toss } | \text{ n tosses}] = \\
&= 6 \cdot [Y=1] + \frac{{1+\dots+5}}{5} \cdot [Y\neq 1] = 6 \cdot [Y=1] + 3 \cdot [Y\neq 1]

\end{align}
$$
Find E(Y|X)
$$
\begin{align}
&\mathbb{E}[Y|X] = \mathbb{E}[\text{n tosses } | \text{ first toss value}] = 1  \cdot  [X=6] + E[G\left( \frac{1}{6} \right)]  \cdot  [X\neq 6] =  \\
&[X=6] + \frac{1}{\frac{1}{6}}  \cdot  [X\neq 6] = [X=6] + 6 \cdot [X\neq 6]
\end{align}
$$

(b) $Var(X | Y ), Var(Y | X)$
$$
\begin{align}
&Var(X\mid Y) = E[(X\mid Y)^{2}] - E[X\mid Y]^{2} \\
&E[(X\mid Y)^{2}] = E[X^{2}\mid Y] = 36 \cdot [Y=1] + 9  \cdot [Y\neq 1]  \\
&Var(X\mid Y) =  E[X^{2}\mid Y] =\cancel{  36 \cdot [Y=1] } + \cancel{ 9  \cdot [Y\neq 1] } - \cancel{ 36[Y=1] } - \\
&\cancelto{ 0 }{ 36[Y=1][Y\neq 1] } - \cancel{ 9[Y\neq 1] } = 0 \\ \\

&Var(Y\mid X) = E[Y^{2}\mid X] - E[Y\mid X]^{2} = [X=6] + 36 \cdot [X\neq 6] - [X= 6] - \\
&- 2 \cdot 6[X=6][X\neq 6] - 36[X\neq 6] = 0
\end{align}
$$


# N6
![[Pasted image 20231019231901.png]]

(a)
$$
\begin{align}
&\sigma(X) = \{ \emptyset, \Omega, \{ -1 \}, \{ 0 \}, \{ 1 \}, \{ -1,0 \}, \{ -1,1 \}, \{ 0, 1 \} \}  \\
 &\Omega_{X} = \{ -1, 0, 1 \}\\
&\sigma(Y) = \{ \emptyset, \{ 0 \}, \{ 1 \}, \Omega \} \\
&\sigma(X \cdot Y) = \{ \emptyset, \Omega, \{ -1 \}, \{ 0 \}, \{ 1 \}, \{ -1,0 \}, \{ -1,1 \}, \{ 0, 1 \} \} \\
&X \cdot Y \in \{ 0,1,-1 \}
\end{align}
$$
(b)
$$
\begin{align}
&coord(\sigma(X,Y)) = coord\left(  \{ \{ -1, 0 \}, \{ 0, 0 \} , \{ X=1, Y \neq 0 \}, \dots\} \right) = 2^{6} = 64 \\
&coord( \sigma(X+Y) ) = coord\{ P(-1,0,1,2) \} = 2^{4} = 16 \\
&coord[\sigma(X, Y,X+{Y}) ] = 2^{24}
\end{align}
$$
![[2023-10-14 Homework SP1 2023-10-19 23.50.18.excalidraw]]
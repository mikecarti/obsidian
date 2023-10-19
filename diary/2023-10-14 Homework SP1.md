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
Each day the Random Restaurant is independently closed with probability p. If the restaurant is open then the number of clients has Poisson distribution with mean µ.

After N days (working or non-working) the Random Restaurant will permanently close, N is random and has Poisson distribution with mean n.

(a) Find the moment generating function of the number of clients during day 1, assuming N $\geq$ 1.

$$
\begin{align}
&X \text{ - number of clients a day} \\
&X \sim Poisson(\mu)  \\
&f(X=k) = {\displaystyle {\frac {\lambda ^{k}e^{-\lambda }}{k!}}} \\
&M_{X(t)} = E(e^{tX}) = \sum_{x}e^{tX}f_{X}(x) = \sum_{x=0}^{\infty} \left(    e^{tX}{\frac {\lambda ^{x}e^{-\lambda }}{x!}}\right)= \\
=&  
\end{align}
$$

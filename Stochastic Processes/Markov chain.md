
The simplest type of processes. 

A Markov chain or Markov process is a [[stochastic model]] describing a sequence of possible events in which the [[probability]] of each event depends only on the state in the previous event.

![[Pasted image 20230902104541.png]]

$$
v_{2} = P \cdot v_{1}
$$
for matrix $P_{\;i \: \to \; i+1}$




![[Pasted image 20230901013513.png| 400]]
$$(\text{Finite states Markov chain})$$
Applicable when there is no memory (correlation) in a process

# Markov Assumption 
is that when you are at a some point trajectory forward is not in any way dependent on path that were taken to get here.

Example: 
If Apple's share worth 100$, You should make a decision solely based on that it is worth 100\$ at that point.

### Basic state:
Starting state for example (1, 0) if i know that i am sleeping right now.

Tasks:
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


![[Pasted image 20230905155207.png]]

a) ![[Markov chain 2023-09-05 15.52.27.excalidraw]]

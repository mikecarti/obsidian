
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

$$
P = \begin{bmatrix}

\end{bmatrix}  
$$


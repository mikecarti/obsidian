A type of [[Markov Processes]]
The simplest type of processes. Used in [[General Adversarial Network]]s for analyzing artifacts.

## Definition

A Markov chain or Markov process is a [[stochastic model]] describing a sequence of possible events in which the [[probability]] of each event depends only on the state in the previous event.


## Transition Matrix
![[Pasted image 20230902104541.png]]

$$
v_{2} = P \cdot v_{1}
$$
for matrix $P_{\;i \: \to \; i+1}$




![[Pasted image 20230901013513.png| 400]]
$$(\text{Finite states Markov chain})$$
Applicable when there is no memory (correlation) in a process

## Markov Assumption 
is that when you are at a some point trajectory forward is not in any way dependent on path that were taken to get here.

Example: 
If Apple's share worth 100$, You should make a decision solely based on that it is worth 100\$ at that point.

## Markov Chain properties
- Markov Chain may not have unconnected nodes.


## [[Homogeneous]] Markov Chain
The chain $X_N$ is homogeneous if its transition probabilities do not depend on the time (value of n)
$$
P(X_{n+1}=j|X_{n} = i) = P(X_{1}=j|X_{0} = i)  
$$
## Recurrent / Terminal State
If we can get back to state that we are now in. In some number of n, such state is called Recurrent (Persistent).

If we have to stay in the same state, that is called terminal state (sometimes terminal state may be recurrent if state has a self-connection and no other connections).

# Idea:
Cluster - area of space, where objects are located closer to each other, than in other places. We want to find dense areas in feature spaces.

$$
\begin{align}
G = (X, E) \quad \quad  X - \text{ training data}
\end{align}
$$
How to make Edges?
1) $x_{i}$ connect with $x_{j}$  , if $\rho(x_{i}, x_{j})< \delta$
2) fully connected graph 
$$
w_{ij} = \exp\left( -\frac{\lvert\lvert x_{i}-x_{j} \rvert\rvert ^{2}}{2\sigma^{2}} \right)
$$
3) $x_{i}$ connects with k nearest neighbors from $X$

![[Graph Laplacian]]


We build [[Specter of the Matrix]] of a Laplacian
[[Eigenvector]]s of [[Graph Laplacian]] are good features. 
![[Pasted image 20240301155204.png]]
![[Pasted image 20240301155212.png]]


# Algorithm of Spectral Clusterization:
1. $X \to G= (X,E) \to L=D-W$                                                                                                                             $\mathcal{O}(l^{2})$
2. $L \to m$ smallest [[Eigenvalue]]s (accounting the multiple), u1, ..., $u_{m}$ - [[Eigenvector]]s ([[Specter of the Matrix]])   $\mathcal{O}(l^{3})$
3. $U = (u, \mid\dots \mid u_{m}) \, \in \,R^{l\times m}$ - new features for our samples                                                                                 $\mathcal{O}(l_{m})$
4. Run some basic algorithm for Clusterization ([[K-Means]], [[K Nearest Neighbors (KNN)]])

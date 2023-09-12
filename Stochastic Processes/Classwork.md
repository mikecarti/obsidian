
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

$$
Q(w)=\frac{1}{\ell}\sum_{i=1}^{\ell}q_{i}(w)
$$

$$
z_{i}^{0}=\nabla q(w^{0})
$$
SAG Iteration:
$i_{k}~{1,\dots,\ell}$
$$
z_{i^{k}}= \begin{cases}
\nabla q_{i}(w^{(k-1)}), i =i_{k} \\
z_{i}^{(k-1)} , i\neq i_{k} 
\end{cases}
$$
$$
\nabla Q(w^{k-1})\approx \frac{1}{\ell}\sum_{i=1}^{n}z_{i}^{(k)}
w^{(k)}=w^{(k-1)} - \eta_{k}  \cdot  \frac{1}{\ell}\sum_{i=1}^{\ell}z_{i}^{(k)}
$$
$$
\mathbb{E}(Q(w^{(k)})-Q(w_{*})) = \underline{O}\left( \frac{1}{k} \right)
$$
![[Pasted image 20230922123142.png]]
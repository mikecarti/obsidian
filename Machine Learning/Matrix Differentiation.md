## Application
Fast Differentiation in ML
## Definition 
Let $L$ be a differential for matrices
$$
\begin{align}
f(x+dx)&=f(x)= f'(x)dx + \bar{o}(dx) \\
f(x+dx)&= f(x) + L[dx]+\bar{o}(|| dx||) \\

\end{align}
$$

Let rows represent [[Domain and Range|domain]] and columns represent [[Domain and Range|range]], then:

$df( \cdot)=$ ...

|        | Scalar | Vector | Matrix |  
|--------| -------- | -------- | -------- |  
| Scalar| f'(x)dx | $J dx$ | - |  
| Vector| $\nabla f(x)dx$ | $Jdx$ | - |
| Matrix| $tr(\nabla_{A}f^{T}dA )$ | 3D tensor | - |

## Properties of Matrix Differentials
properties are really similar to common differentials, but it is important to remember that we are working with matrices:
1) $d(AB) = dAB + AdB$,     $dAB\neq BdA$
2) $d(\alpha A+\beta B) = \alpha dA + \beta dB$     (where $\alpha, \beta$ are scalars)
3) $d(A^{T})=(dA)^{T}$
4) $dC = 0$     for a constant matrix $C$
6) $s \in R^{1\times1} \implies s^{T}=s \quad tr(s)=s \quad sA = As$ 
7) $\left< x,Ay \right>=\left< A^{T}x,y \right>$

## Useful Differentials
1) $d(A^{-1}) = -A^{-1}dAA^{-1}$
2) $d (det \,A) = tr(det(A)A^{-1} dA)$
3) $\nabla_{A}tr(A) = I_{n}$
4) $d \left< A,X \right> = \left< A, dX \right>$


## Examples
### 1)
$$
\begin{align}
f(x) = <a,x> \\
f(x+dx) = <a,x+dx> = <a,x>+ <a,dx> \\
\nabla f(x)=a
\end{align}
$$
### 2)
Note:
$$
\begin{align}
d(\alpha A + \beta B)= \alpha dA + \beta dB \\
d(AB) = \dots \\
d(A^{T}) =  (dA)^{T}
\end{align}
$$
Then:
$$
\begin{align}
f(x)&=x^{T}Ax \\
d((x^{T})(Ax))&= (dx^{T})Ax+x^{T}d(dx) = d(x^{T})Ax + x^{T}(dA \cdot x + Adx) =  \\
d(x^{T})Ax + x^{T}Adx&=x^{T}A^{T}dx + x^{T}Adx = x^{T}(A+A^{T})dx = <(A+ A^{T})x, dx>
\end{align}
$$

### 3)
$$
f(X) = a^{T}XAXa
$$
a - $n \times 1$
X - $n \times n$
A - $n \times n$

$$
\begin{align}
df(x)= da^{T}(XAXa)+a^{T}d(XAXa)= \\
 a^{T} (dXAX \cdot a + XAXda)=  \\
a^{T}(dX \cdot AX+ X \cdot dAX)a =  \\
a^{T}dXAXa + a^{T}XAdXa =  \\
\end{align}
$$
Note:
$$
tr(\nabla f(x)dx)
$$
$$
\begin{align}
=\mathrm{Tr}(a^{T}dxAXa + a^{T}XAdXa) = \\
\mathrm{Tr}(dXAXaa^{T} + dXaa^{T}XA)= \\
\mathrm{Tr}(dx \cdot (AXaa^{T}+aa^{T}XA)) = \\
\mathrm{Tr}(g^{T} \cdot dx^{T}) \\
\nabla F(x)=g
\end{align}
$$
### 4) 
Note: $d(x^{T}dx) = (A+A^{T})x^{T}dx = 2x^{T}dx$

$$
\begin{align}
f(x)=xx^{T}x \\
\nabla_{x}f(x)=? \\
d(xx^{T}x)=(dx)x^{T}x + xd(x^{T}x) =  \\
(dx)x^{T}x+2x \cdot x^Tdx= \\
(x^Tx)dx + 2xx^Tdx= \\
(Ix^Tx+2x \cdot x^T)dx
\end{align}
$$
### 5) 
Gradient Of Matrix Determinant
$$
\begin{gather}
\nabla_{X}\det X = ? \\
\text{Decomposition for i-th row} \\
\det X=\sum_{k=1}^{n}(-1)^{i+k}X_{ik}M_{ik} \\
\text{Where } M_{ik} \text{ is a minor of row i, column k} \\
\frac{\delta}{\delta x_{ij}}\det X=\frac{\delta}{\delta X_{ij}}\sum_{k=1}^{n}(-1)^{i+n}X_{ik}M_{ik} \\
M_{ik}\text{ is not dependent on } X_{ij} \\
= (-1)^{i+j}M_{ij} \\
\left( \frac{{\delta \det X}}{\delta X_{ij}} \right)^n_{i, j=1} \\
(X^{-1})_{ij}=\frac{1}{\det X}(-1)^{i+j}M_{ij} \\
\text{Combining the formulas we get: } \\
\nabla \det X=(\det X)X^{-T} \\
\dots \text{Further solution}
\end{gather}
$$

### 6) 
$$
\begin{align}
\nabla_{A}\mathrm{Tr}(AB)  \\
d\mathrm{Tr}(AB)=\mathrm{Tr}((dA)B+AdB)=\mathrm{Tr}(B \cdot dA) \\
\end{align}
$$

### 7) 
Composite function
$$
\nabla_{X}g(f(x)) = g'(f(x)) \nabla_{X}f(x)
$$
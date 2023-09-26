
## Definition
$$
\begin{align}
f(x+dx)&=f(x)= f'(x)dx + \bar{o}(dx) \\
f(x+dx)&= f(x) + L(dx)+\bar{o}(|| dx||) \\

\end{align}
$$

|        | Scalar | Vector | Matrix |  
|--------| -------- | -------- | -------- |  
| Scalar| f'(x)dx | $J dx$ | - |  
| Vector| $\nabla f(x)dx$ | $Jdx$ | - |
| Matrix| $tr(\nabla_{A}f(A)^{T}dA )$ | - | - |
## Application
Fast Differentiation in ML

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
(x^Tx)dx + 2xx^Tdx
\end{align}
$$


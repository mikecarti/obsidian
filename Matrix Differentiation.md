
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


$$
$$

$$
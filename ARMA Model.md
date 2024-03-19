# ARMA Equation
$$
A( L)  \cdot  (y_{t}-\mu) = M(L) \cdot u_{t}
$$
where $u_{t}$ - [[White Noise]] and A, M are [[Lag Operator]] [[Polynomial]]s.

## Different Definitions
1) ARMA-model - any solution of ARMA equation
2) ARMA-model - the stationary solution of ARMA equation
3) ARMA-model - the stationary solution of ARMA equation that can be written in the [[MA Process]] form

# Theorem 1 (Number of solutions)
If $deg(A (L)) \geq 1$: 
number of solutions is infinite.

if $deg(A(L))=1$ (there is no lag in polynomial). Then equation has one unique solution.

# Theorem 2 (Number of stationary solutions)
If A(L) and M(L) are [[Coprime Polynomial]]s, then eq-n
$$
A( L)  \cdot  (y_{t}-\mu) = M(L) \cdot u_{t}
$$
Has unique stationary solution iff A(L) has no such root $l$:  $\mid l\mid=1$
If there is such root => there are no [[Stationarity|stationary]] solution.

# Theorem 3
### Motivation
in economic applications $u_{t}$ is not just a [[White Noise]], but a shock, that happens at $t$, and is independent of past event

### The Theorem
z is a root of $A(L)$ iff $\frac{1}{z}$ is a root of $char_{A}(\lambda)$. ([[Characteristic Equation]])

# Theorem 4
If A(L) and M(L) are coprime, then equation:
$$
A(L) \cdot (y_{t}-\mu) = M(L)  \cdot u_{t}
$$
has unique solution of the form:
$$
y_{t} = \mu + u_{t} + \alpha_{1}u_{t-1} + a_{2}u_{t-2} + \dots
$$
iff all roots $\lambda$ of $char_{A}(\lambda)$ are $\mid\lambda \mid<1$

(that solution is also [[Stationarity|stationary]] and is called [[MA Process]])

# Assumptions
- $y_{t}$ is [[Stationarity|stationary]] 
- $y_{t} = \mu + a_{1}u_{t-1}+a_{2}u_{t-2}+\dots$
- $A(L)=1-b_{1}L$
- $M(L) = 1+\gamma_{1}L$
- $A(L), M(L)$ - coprime

# Parameters to be estimated: 
$$
\hat{b_{1}}, \hat{\gamma}_{1}, \hat{\mu}, \hat{\sigma^{2}}
$$

# Optimization Function
[[Maximum Likelihood Estimation (MLE)]]

$$
\begin{align}
L = f(y_{1}, y_{2}, \dots, y_{T} \mid \theta) \neq f(y_{1})  \cdot  \dots  \cdot  f(y_{T}) \\
\text{As we have normal distribution for } u_{t} \text{ (therefore for y as well} \\
y = \begin{bmatrix}
y_{1} \\
\dots \\
y_{T}
\end{bmatrix} \sim \mathcal{N}\begin{pmatrix}
\begin{pmatrix}
\mu \\
\dots \\
\mu
\end{pmatrix}; 
\mathcal{C}
\end{pmatrix} \quad \mathcal{C} - \text{Covariate matrix } T \times T 
\end{align} \quad 
$$
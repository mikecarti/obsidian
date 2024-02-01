
$$
(W_{t}) \xrightarrow[]{\text{stochastic integral}} \text{Martingales}
$$
### Motivation
For stochastic processes old rules of integration do not work! But the economics interpretation does. So old [[Newton-Leibniz]] formula does not work for that

### Definition
$W_{t} \sim Y_{t}$ is our approximation ($Y_{t}$ is piece-wise discretization of continuous $W_{t}$)
$$
\int _{0}^{T} \, Y_{t}dW_{t} = -W_{0} \cdot W_{0} - \underbrace{ \sum_{i=1}^{n}W_{\frac{2T}{n}}\left( W_{\frac{it}{n}}-W_{\frac{(i-1)t}{n}} \right) }_{ \text{intermediate transactions } =\, S   }  + \underbrace{ W_{T} \cdot W_{T} }_{ \text{final payoff}}
$$

### Better Definition
$$
\int _{0}^{T}W_{t}dW_{t} = \underbrace{ -\frac{T}{2} + \frac{W_{T}^{2}}{2} }_{ martingale }
$$
## Shorthand notation
Normally $a=b$ means a and b are the same object.
$$
\begin{align}
&\text{We write: }dX_{t}= A_{t} \cdot dW_{t} + B_{t}dt \\
&\text{We mean: }X_{t} = X_{0}+ \int _{0}^{t}A_{u} \cdot dW_{u}+ \int _{0}^{t}B_{u}du  \\
&\text{That means that } X_{t} \text{ is locally differentiable}
\end{align}
$$
$dX_{t}$ does not exist, it is not a random variable. It's not a constant, it's just a **shorthand**.

$B_{t}$ - regular calculus differentiable function (noise / randomness)

We write:                                                          We mean: 
![[Pasted image 20231117164400.png]]

![[Pasted image 20231117164642.png]]

### under mild technical assumptions
$$
\int _{0}^{T}\text{Anything}_{t} \, dW_{t} = M_{T}
$$



### Proof of better definition
To remove dependence of different $W_{k}$ lets rewrite $S$ as a sum of independent terms by [[Wiener Process (Brownian Motion)#Properties|increment independence property]]. 

$$
\begin{align}
&S = { \sum_{i=1}^{n}W_{\frac{2T}{n}}\left( W_{\frac{it}{n}}-W_{\frac{(i-1)t}{n}} \right) } \\
&A = \sum_{i=1}^{n}\left( W_{\frac{iT}{n}}-W_{\frac{(i-1)T}{n}} \right)^{2} \xLeftarrow[]{} \text{ sq. sum of independ. terms} \\
&V_{i} =  W_{\frac{iT}{n}} \\
&A = \sum_{i=1}^{n}V_{i}^{2} + \sum_{i=1}^{n}V_{i-1}^{2} - 2\sum V_{i} \cdot V_{i-1} =  \\
&= 2\sum_{i=1}^{n}V_{i}^{2} - 2\sum V_{i} \cdot V_{i-1} - V_{n}^{2} + \cancelto{ 0 }{ V^{2}_{0} } \\
&\sum V_{i}^{2 } - \sum V_{i}V_{i-1} = \frac{\sum(V_{i}-V_{i-1})^{2} + V^{2}_{n}}{2} \implies \\
&\implies \int _{0}^{T}Y_{t}dW_{t} = - \sum(V_{i}- Y_{i-1})^{2} + \frac{V_{n}^{2}}{2}  \\
&\int _{0}^{T}Y_{t}dW_{t} = - \sum - \frac{\sum\left( W_{\frac{iT}{n}}- W_{\frac{(i-1)T}{n}} \right)^{2}}{2} + \frac{W^{2}_{T}}{2}
\end{align}
$$

Here we need to use [[L2 limit]].
$$
\begin{align}
&R_{n} = - \frac{{\sum\left( W_{\frac{it}{n}}- W_{\frac{i-1}{n}} \right)^{2}}}{2} \to_{n\to \infty}^{L^{2}} ? \\
&E(R_{n} ) = -\frac{1}{2}n \cdot E \left( \left( W_{\frac{iT}{n}}-W_{\frac{(i-1)T}{n}} \right)^{2} \right) = -\frac{n}{2} \cdot \frac{T}{n} \cdot -\frac{T}{n} \\
&Var(R_{n}) = \frac{1}{4}n \cdot Var(\Delta_{i}^{2}) =\dots\\
&\Delta_{i} \sim N\left( 0; \frac{T}{n} \right) \\
&z = \frac{\Delta_{i} - 0}{\sqrt{ \frac{T}{n} }} \sim N(0;1) \\
&\dots= \frac{n \cdot T^{2}}{4n^{2}} \cdot Var(z^{2}) \to_{n\to \infty} 0 \\ \\
&E(R_{n}) = -\frac{T}{2} \\
&Var(R_{n}) \to 0
\end{align}
$$



### Economic Interpretation Of The basic Integral
$$
\begin{align}
&\int _{a}^{b}f(t) \, dt  \\
&\int _{a}^{b}q(t)\,dp(t)   \\
&\int _{a}^{b}t^{2}dt  \quad q(t)=t^{2} \, \quad p(t)=t \\
&\int _{a}^{b}p(t)\,dp(t)  \quad \text{= the net profit}
\end{align}
$$

$p(t)$ - price of the asset
$q(t)$ - my trading strategy (how many do i keep in my financial portfolio)

Examples in [[Classwork (Stochastic Processes)##10.11(Lecture)|Classwork]]



### Idea
When you need to find a stopping time, try to imagine that there is a Casino, in which some people play.


## Definitions

![[Pasted image 20231020171332.png]]


## Examples

### Monkey Example
![[Pasted image 20231020171427.png]]

Rule 3: 
Every player bets on $A$ then on $B$, then on $R$ $ABRACADABRA$

$t = \tau$ = $M_{A}$
Monkey actually types .......  $ABRACADABRA$
Player $\tau$ gets $26$
Player $\tau - 10$ gets $26^{11}$
Player $\tau-4$ gets $26^{4}$

$$
\begin{align}
M_{n} = S_{n} - n \\
M_{\tau} = S_{\tau} - \tau \\
M_{n} \text{ - is martingale} \\
\tau \text{ - is stopping time} \\
\mathbb{E}(M_{\tau}) = M_{0} = S_{0} - 0 = 0 \\
\mathbb{E}(26^{11}+26^{4}+26-\tau)=0 \\
\mathbb{E(\tau)} = 26^{11}+26^{4}+26^{1}
\end{align}
$$

### Betting Example

choose Red (1/2) or Black (1/2)
Initially we have 100$
and every moment of time i bet 1$ on Red color.
$X_{0} = 100$ 
$X_{n+1}=X_{n}+W_{n+1}$             $P(W_{n+1}=1)=\frac{1}{2}=P(W_{n+1}=-1)$
$$
\tau = min(t\,|\,X_{t}=0 \text{ or }X_{t=220})
$$
1) $P(X_{\tau}=220)$?
2) $\mathbb{E}(\tau)$?

1)
$$
\begin{align}
&\mathbb{E}[X_{\tau}]= 0 \cdot (1-p)+220p \\
&\text{Doob's Theorem: you cant make money (on avg) if you play a honest game} \\
&\mathbb{E}[X_{\tau}]=X_{0}=100 \\
&200 \cdot p =100 \implies p = \frac{100}{220}
\end{align} 
$$
2)
Lets create a [[Martingale]] 
$$
\begin{align}
Y_{n} = (X_{n}-100)^{2} - n  \\
\mathbb{E}
\end{align}
$$

### Related:
[[Doob's Theorem]]

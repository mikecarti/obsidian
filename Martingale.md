![[Pasted image 20231020171332.png]]


## Example
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
\mathbb{E}(26^{4}+26^{4}+26-\tau)=0 \\
\mathbb{E(\tau)} = 26^{11+}
\end{align}
$$
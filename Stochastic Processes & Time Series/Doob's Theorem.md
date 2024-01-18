In simple words, we can not gain from a fair game

$$
\begin{align}
\text{If:}& \\
&1) (X_{n})\text{ is a martingale:} \; E\left[ X_{n+1}\mid X_{n},X_{n-1},\dots,X_{0} \right] =X_{n} \\ \\

&2) \text{Stopping time }\tau \quad  \{ \tau\leq n \} \, \in \,\sigma(X_{n}, X_{n-1}, \dots, X_{0}) \\
&\text{(Your decision to stop the game does not depend on future} \\ \\
&3)  \text{(technical) } P(\tau<+\infty) \quad \quad  \exists \;m: \; \mid X_{min(\tau,n)} \mid\leq m \\
\text{Then}&: \\
&E[X_{\tau}] = E[X_{0}] \quad  \text{Where } \tau \text{ - moment when you quit the game} \\
&\text{And } X_{\tau} \text{ - your final fortune}
\end{align}
$$

$$
\begin{align}
p(x) = \underbrace{ \lim_{ h \to 0 } \frac{1}{2h}\mathbb{P}(\zeta \, \in \,\left[ x-h, x+h \right] )  }_{ \hat{p}(x)=\frac{1}{2h} \frac{1}{l}\sum_{i=1}^{l}\left[ \mid x - x_{i}\mid <h \right]  }\quad  \text{h - window width}  \\
\hat{p}(x)=\frac{1}{2h} \frac{1}{l}\sum_{i=1}^{l}\left[ \mid x - x_{i}\mid <h \right] =  \frac{1}{lh} \sum_{i=1}^{l} \frac{1}{2}\left[ \frac{{\mid x-x_{i}\mid}}{h} <1 \right] 
\end{align}
$$

Thus we get an estimate of density:
![[Pasted image 20240209122613.png]]

Would be better if it was more smooth ([[Parzer Kernel]])
$$
\begin{align}
\frac{1}{2}\left[ z<1 \right] \approx K(z) - \text{Parzer Kernel} \\
\hat{p}(x) = \frac{1}{lh}\sum_{i=1}^{l}K\left( \frac{{\mid x-x_{i}\mid}}{h} \right) \\
K(z)= \frac{1}{\sqrt{ i\pi }}e^{-z^{2}/2}
\end{align}
$$
##### Multi-Dimensional Case
$$
\begin{align}
\hat{p}(x) = \frac{1}{lV(h)}\sum_{i=1}^{l}K\left( \frac{{\rho(x,x_{i})}}{h} \right) \\
V(h) = \int K\left( {\frac{\rho(x,x_{i})}{h}} \right) \, dx 
\end{align}
$$
+Restore [[Probability Density Function (PDF)]] of any complexity
-[[Curse Of Dimensionality]]

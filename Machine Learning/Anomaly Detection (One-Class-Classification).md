$X=(x_{i})_{i=1}^{l}$ - представители одного ("нормального") класса

We want: 
from training class <-$a(x)$-> something new

# How to formalize anomality
## Statistical approach
$x_{i} \sim p(x\mid\theta)$ - assuming that X has distribution p

if we find $p(x\mid\theta)$, then 
$a(x) = [p(x\mid\theta)<t]$

### How to find $p(x\mid\theta)$
#### Parametric Approach
$p(x\mid\theta)$ - belongs to some family of [[Distribution]]s (Normal, Exponential, [[Mixture Model]])

But data is complex, density function may be not suitable.

#### Non-Parametric Approach
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



![[Imbalanced Data]]
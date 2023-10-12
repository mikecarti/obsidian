
$$
\begin{align}
&\mu_{B} = \frac{1}{n}\sum_{i=1}^{n}x_{B,j} \\
&\sigma_{B}^{2} = \frac{1}{n}\sum_{i=1}^{n}(x_{B, j}- \mu_{B})^{2} \\
&X_{B,j} - \text{ j-й объект в батче B} \\ \\


& \hat{x}_{i} = \frac{{x_{i} - \mu}}{\sqrt{ \sigma^{2}+\epsilon }}  \\
&y_{i} = \hat{x}_{i} \circ w + \beta \qquad w,\beta\in \mathbb{R}^{N} 
\end{align}
$$
$a \circ b$ - [[Hadamard Product]] 


## Problem
Different scale of data, may affect significantly next layers of neural network. So let us normalize objects' features batch-wise (we count mean and standard deviation)

## Note
- Usually put between full connected / convolutional layer and non-linearyty
- Helps increase step size for [[Gradient Descent]]
- Wanted to create it to 


### Train mode:
$$
\begin{align}
& x \in \mathbb{R}^{B\times N} \quad x_{i}\in \mathbb{R}^{N}\\
& \mu = \frac{1}{B}\sum_{i=1}^{B}x_{i} \quad x_{i} \text{ - vector}\\
& \sigma^{2} = \frac{1}{B}\sum_{i=1}^{B}(x_{i}-\mu)^{2} \quad \sigma^{2} \text{ - vector}\\ \\

& \hat{x}_{i} = \frac{{x_{i} - \mu}}{\sqrt{ \sigma^{2}+\epsilon }} \quad \epsilon \text{ - for not getting 0 denom.}  \\ \\

&\frac{1}{B}\sum_{i=1}^{B}\hat{x}_{i} = 0  \\
&\frac{1}{B}\sum_{i=1}^{B}\hat{x}_{i}^{2} = 1  \\ \\

&y_{i} = x_{i} \odot w + \beta \qquad w,\beta\in \mathbb{R}^{N} \text{ (because 0 mean is bad)}\\ \\

& w, \beta  \text{ - trainable by grad. descent}
\end{align}
$$

$$
\begin{align}
&Forwarding: \\
&running_{mean} \quad running_{var} \in \mathbb{R}^{N} \\
&running_{mean} := running_{mean}(1-m) + \mu \cdot m \quad m =0.1 \\
&running_{var}:= running_{var}(1-m)+\sigma^{2}m \cdot \frac{B}{B-1}
\end{align}
$$

### Eval. mode / Inference mode:
$$
\begin{align}
&\hat{x}_{i} = {x_{i}} - \frac{running_{mean}}{\sqrt{ running_{var}+\epsilon }} \\
&y_{i} = \hat{x}_{i} \odot w + \beta
\end{align}
$$

## Related:
[[Neural Network]]
[[2D-Batch Norm]]

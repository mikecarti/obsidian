# Motivation
[[Mixture Model]] has too complex functions for gradient descent, but maybe the idea of several distributions belongs to other class of problems.

# Applications
![[Mixture Model#Another way for PDF]]

# [[Maximum Likelihood Estimation (MLE)]]
$$
\begin{align}
&\log\;p(X\mid \theta) \to \max_{\theta} \text{ - initial likelihood} \\
&\log p(x, z \mid \theta) \to \max_{\theta, t} \text{ - complete likelihood} \\
&X \text{ - observed variables (training set)} \\
&z \text{ - latent variables} \\
&\theta \text{ - parameters}
\end{align}
$$

It is often that we meet such tasks with parameters and latent variables

# EM in General Case
Could be proved:
$$
\begin{align}

&\log p(X\mid \theta) = L(q,\theta) + KL(q\mid \mid p) \quad \text{ for any distribution q(z)} \\
&L(q,z\theta)=\sum_{z}q(z)\log\frac{{p(x,z\mid \theta)}}{q(z)}  \\
&KL(q\mid \mid p)=\sum_{z}q(z)\log\frac{{p(z\mid X, \theta)}}{q(z)} \\
&\log p(X\mid \theta) = L(q,\theta) + KL(q\mid \mid p) \geq \underbrace{ L(q,\theta) }_{ \text{Lower bound for MLE} } \\
\end{align}
$$
Step 1:
$$
KL(q\mid \mid p)=0 <=> q^{*}(z) = p(z\mid X, \theta) 
$$ $q^{*}$ - [[Aposterior Distribution]].

Step 2: 
$$
\begin{align}
L(q^{*}, \theta) \to \max_{\theta} \\
L(q^{*}, \theta) = \sum_zq^{*}(z)\log{\frac{p(x,z\mid \theta)}{q^{*}(z)}} =  \\
= \sum_{z}q^{*}(z)\log p(x,z\mid \theta) - \sum_{z}q^{*}(z)\log q(z) \\
Q(\theta, \theta^{old}) = \mathbf{E}_{z\sim q^{*}(z)}\log p(x,z\mid \theta) \to \max_{\theta}
\end{align}
$$


[[Kullback Leibler Divergence (KL-Loss)]]

# Techniques
## "Zero" Approach
$$
\log p(x,z\mid \theta) \to \max_{z, \theta}
$$
Optimization will not be able to solve it with big probability.


## First Approach. Block-Coordinate-Wise Descent by $z, \theta$ 
Similar to [[Dropout]].
Step A:
$$
z^{*} = \operatorname*{argmax}_{z} \log p(X,z\mid \theta^{all})
$$
Step B:
$$
\theta^{new} = \operatorname*{argmax}_{\theta} \log p(X,z^{*}\mid \theta) 
$$
converges badly, no convergence conditions.

## Second Approach (EM)

Step 0: initialize $\theta$

Step E (expectation):
$$
p(z\mid X, \theta^{old}) \text{ - compute aposterior distribution}
$$
[[Aposterior Distribution]]

Step M (Maximization):
$$
Q(\theta, \theta ^{old}) = \mathbf{E}_{z\sim p(z\mid X, \theta^{old})}\log p(X, z\mid \theta) \to \max_{\theta}
$$
Compute [[Expected Value]] by summing up values from an [[Aposterior Distribution]] of $z$ with weighted sum, where weights are probabilities of an estimated [[Aposterior Distribution]].

# Connection between EM-Algorithm and [[Gradient Descent|Gradient Lifting]]

Paper: Optimization with EM and Expectation-Conjugate Gradient.

$$
\begin{align}
\log p(X\mid \theta) \to \max_{\theta} \equiv \text{Gradient Descent} 
\end{align}
$$
![[Mixture Model#Statement 1]]

$$
\begin{align}
&\theta^{i+1} = M(\theta^{i}) \text{ - result of M step} \\ \\
&\text{From statement 1:} \\
&(*) \quad  \theta^{i+1}-\theta^{i}=P(\theta^{i}) \cdot \nabla_{\theta}\log p(X\mid \theta^{i}) \quad  \text{ - differentiate by }\theta^{i}  \\
&M'(\theta^{i}) - I = p'(\theta^{i})\underbrace{ \nabla \log p(x\mid \theta^{i}) }_{ \approx 0, \;\text{when we close to local min. or plato} } + p(\theta^{i}) \nabla_{\theta}^{2}\log p(x\mid\theta^{i}) \\
&\text{Assume we are there } \^ \\
&M'(\theta^{i}) - I \approx P(\theta^{i}) \underbrace{ \nabla_{\theta}^{2}\log p(X\mid\theta) }_{ =S(\theta^{i}) \text{ - Hessian} } \\
&P(\theta^{i}) = (I-M'(\theta^{i}))(-S(\theta^{i}))^{-1} \\
&\text{If Eigenvalues of } M'(\theta') \text{ are close to 0}, \text{ then } \\
& I - M'(\theta^{i}) \approx I, \text{ then:} \\
&P(\theta^{i}) \approx (-S(\theta^{i}))^{-1} \\
&\implies M(\theta^{i}) - \theta^{i} = (-S(\theta^{i}))^{-1}\nabla_{\theta}\log p(X\mid\theta^{i})
\end{align}
$$



# Example: [[Mixture Model]] for [[Normal Distribution]]
E-step:
![[Pasted image 20240202115345.png]]

![[Pasted image 20240202115331.png]]



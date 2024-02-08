The idea behind this method is to estimate such parameters for which observed data has the maximum joint probability (data is more probable to appear with such parameters of [[Joint Probability Distribution]].)

# Intuition
Select such parameters of distribution, that make observed data most probable. It is the probability that we would observe what we actually do observe in our data.

# Formally
$$
\begin{align}
&{\displaystyle \;\theta =\left[\theta _{1},\,\theta _{2},\,\ldots ,\,\theta _{k}\right]^{\mathsf {T}}\;} - \text{parameters}\\
&\mathbf{y} = \left( y_{1},y_{2}\dots,y_{n} \right) - \text{ observed data sample} \\
&{\displaystyle {\mathcal {L}}_{n}(\theta )={\mathcal {L}}_{n}(\theta ;\mathbf {y} )=f_{n}(\mathbf {y} ;\theta )\;,} - \text{Likelihood Function} \\ \\

&\text{For independent and i.i.d R.V,} \quad   \\
&f_{n}(y;\theta)  \text{ will be the product of density functions:} \\
&{\displaystyle f_{n}(\mathbf {y} ;\theta )=\prod _{k=1}^{n}\,f_{k}^{\mathsf {univar}}(y_{k};\theta )~.} \\
&{\displaystyle {\hat {\theta }}={\underset {\theta \in \Theta }{\operatorname {arg\;max} }}\,{\mathcal {L}}_{n}(\theta \,;\mathbf {y} )~.} \\ \\

&\mathcal{L} = \prod_{i=1}^{n} P(X=x_{i}) \to \max_{\theta}
\end{align}
$$

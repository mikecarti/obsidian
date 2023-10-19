# Definition
## Discrete 
$$
\mathbb{E}[X] = \sum_{i=1}^{x}x_{i}p_{i}
$$
## Continuous
$$
\mathbb{E}[X] = \int _{-\infty} ^{+\infty} xf(x)\, dx 
$$

#### Conditional Expectation / Probability
$$
E[X |Y] = \frac{E[ X  \cdot  Y]}{E[Y]}
$$

#### Bayes Theorem
$$
E[X|Y] = \frac{{E[Y|X] \cdot E[X]}}{E[Y]}
$$

## Independency -> Unpredictability -> Uncorrelatedness
#### Independency
$$
P(X \cdot Y)=P(X) \cdot P(Y)
$$

#### Unpredictability
$$
E[X|Y] = E[X]
$$

#### Uncorrelatedness

$$
cov(X,Y) = E[X \cdot Y] - E[X] E[Y] = 0
$$

## Other properties

### Tower Property (because Expected value is based on Y)
$$\begin{align}
E[\;E[XY|Y]\;]=E[XY]
\end{align}
$$


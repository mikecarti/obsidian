1) [[Linear Probability Model (LPM)]]
2) [[Probit Regression]]
3) [[Marginal Effect (ME)]]
4) [[Logarithmic Regression]]
5) [[Auto-Correlation]]
6) Standard Error of coefficients
7) [[Breusch-Godfrey test]]
8) Durbin-Watson statistic
9) [[Wald Test]]*
10) [[Generalized least squares (GLS)]]*
11) [[2 Step Least Squares (2SLS)]]
12) [[Maximum Likelihood Estimation (MLE)]]
13) [[IV]] 
14) Inconsistency, Biasedness, Inefficiency


Read until Chapter 16 (without 13, 14)
1 chapter a day = finish on 21 march

# Current Page
Page 59

# Tasks
## №6
2.OLS estimate is biased as it does not account many factors that also come in play.
3.house area, neighbourhood, distance from subway, whether house in commercial area. yes they may be correlated, for example commercial area or no is definitely correlated variable.

## №7
(1)
$$
sav = \beta_{0} + \beta_{1}inc + u, \quad \quad u = \sqrt{ inc } \cdot e
$$
$$
\begin{align}
prove: E(u\mid inc) =0 \\
E(u \mid inc) = E(\sqrt{ inc } \cdot e \mid inc) =  \\
E(e\mid inc)  \cdot  E(\sqrt{ inc }\mid inc) =  \\
= E(e)  \cdot  E(\sqrt{ inc }) = 0
 \end{align}
$$
(2)
$$
\begin{align}
Var(u\mid inc) = \sigma^{2}_{e}inc ?\\
Var(\sqrt{ inc } \cdot e \mid inc) = inc Var(e \mid inc) = inc  \cdot  Var(e)  =  \\
= inc  \cdot  \sigma^{2}_{e}
\end{align}
$$

(3) As families start having more income, the possibility to save more increases, but not all families wish to save same cash sum, some want to spend lots, therefore variance rises

## №8
(1)

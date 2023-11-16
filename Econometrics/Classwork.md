## 03.10

[[Douglas Production Function]]
[[Multiple Regression Hypothesis Testing (Inference)]]
[[Cochrane's Theorem]]

$$
\begin{align}
H_{0}: R \cdot \beta=q \\
H:  R \cdot \beta \neq q \\
R = \begin{pmatrix}
0 & 0 \\
0 & I
\end{pmatrix} \\ \\
H_{0}: \begin{cases}
\beta_{j1}=0 \\
\dots \\
\beta_{jp} = 0 
\end{cases}

\end{align}

$$

# 16.11 Class 9
Number1
a)
$$
\begin{align}
&y_{i}= \beta x_{i}A+\epsilon_{i} \\
&E(\epsilon_{i}^{2}) = ax^{2}_{i} = Var \\ \\

&OLS: \\
&\hat{\epsilon_{i}} = y_{i}-\hat{\beta}x_{i} \\
&\sum\hat{\epsilon_{i}}^{2} = \sum(y_{i}-\hat{\beta}x_{i} )^{2} =OLS \\
& \frac{dOLS}{d \hat{\beta}} = 0 \implies  \hat{\beta} = \frac{{\sum x_{i}y_{i}}}{\sum x^{2}_{i}} \\
&E\left( \frac{{\sum x_{i}y_{i}}}{\sum x_{i}} \right)  = \dots
\end{align}
$$

b) [[Weighted Least Squares]]
$$
\begin{gather}
\epsilon_{i} \sim N(0, \alpha x_{i}) \\
\frac{\epsilon_{i}}{x_{i}} \sim N(0,a) \\
\frac{y_{i}}{x_{i}} = \beta+\frac{\epsilon_{i}}{x_{i}} \\
\hat{\beta}_{WLS} = \frac{1}{n}\sum{\frac{y_{i}}{x_{i}}} \\
E(\hat{\beta}) = \frac{1}{n}\sum{\frac{\beta x_{i}+E(\epsilon_{i})/}{x_{i}}} = \frac{1}{n}\sum\beta  =\beta \\ \\

Var(\hat{\beta}_{WLS}) = E\left( \frac{1}{n}\sum \frac{y_{i}}{x_{i}} - \beta\right)^{2}  =  \\
= E\left( \frac{1}{n}\sum\frac{{\beta}x_{i}+\epsilon_{i}}{x_{i}}-\beta \right) ^{2} = \\
=\frac{1}{n^{2}}E\left( \epsilon  \frac{{\epsilon_{i}}}{x_{i}}\right)^{2} = \frac{1}{n^{2}}E\left( \sum \frac{{\epsilon_{i}^{2}}}{x_{i}^{2}} + \sum\sum \frac{{\epsilon_{i}\epsilon j}}{x_{i}x_{j}} \right) \quad= \frac{1}{n^{2}}\sum {\frac{E \epsilon^{2}}{X_{i}^{2}}} = \\
= \frac{1}{n^{2}}\sum a = \frac{a}{n}
\end{gather}
$$

c) ...


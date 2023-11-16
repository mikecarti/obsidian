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

# 16.11
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
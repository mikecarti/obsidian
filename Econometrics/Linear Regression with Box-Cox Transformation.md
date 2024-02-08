$$
\begin{align}
y_{i}^{\alpha_{0}} = \beta_{0} + \beta_{1}x_{1}^{(\alpha_{1})} + \dots + \beta_{k}x_{k}^{(\alpha_{k})} + \epsilon_{i} \\
y^{(\alpha)} = \begin{cases}
\ln y, & \alpha=0 \\
y^{\alpha}, & \alpha\neq 0
\end{cases}
\end{align}
$$


[[Linear Regression with Box-Cox Transformation]] coefficients can not be estimated with [[Ordinary Least Squares (OLS)]], but can be estimated with [[Maximum Likelihood Estimation (MLE)]]
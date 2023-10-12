$$
\begin{gather}
\text{Unrestricted Reg: }\quad y_{i} = \beta_{0} + \beta_{1}x_{1i} + \beta_{2}x_{2i}+\beta_{3i} + \epsilon_{i} \\
H_{0}: \begin{cases}
\beta_{1}=0 \\
\beta_{2}=0
\end{cases} \\
H_{A}: [\exists i : \beta_{i} \neq 0]  \\
\text{Restricted Reg: } \quad y_{i} = \beta_{0}+\beta_{3}x_{3i}+\epsilon_{i} \\
F = \frac{{(RSS_{R}-RSS_{UR})}/q}{RSS_{UR}/(n-k)} \quad q - \text{Num. of Lin. Restrictions}
\end{gather}
$$
## Why we use [[Fischer Distribution]]?
$$
F = \frac{{(RSS_{R}-RSS_{UR})}/q}{RSS_{UR}/(n-k)} \sim \frac{\chi_{q}^{2} - \chi^{2}_{q}}{\chi^{2}_{n-k}} \equiv {\frac{\chi^{2}_{q}}{\chi^{2}_{n-k}}} := \text{Fischer}
$$





## Related:
[[F Statistic]]

$$
\begin{gather}
\hat{y} = \ln (y + 1) \\
\hat{MSE} = \frac{1}{l}\sum_{i=1}^{l}(\hat{y} - \hat{a})^{2} = \frac{1}{l}\sum_{i=1}^{n}(\ln(y+1)-\hat{a})^{2} \\
e^{\hat{MSE}} = \exp\left(\frac{1}{l} \sum_{i=1}^{l}(\ln(y+1)-\hat{a})^{2} \right)  \\
{MSE} = \frac{1}{l}\sum_{i=1}^{l}(y-a)^{2} \\
\hat{a}(x_{i}) = \ln (1+a(x_{i})) \\
e^{\hat{MSE}} = \exp\left(\frac{1}{l} \sum_{i=1}^{l}(\ln(y+1)-\ln (1+a(x_{i})))^{2} \right) \\
e^{\hat{MSE}} = \exp\left(\frac{1}{l} \sum_{i=1}^{l}\left( 2\ln\frac{(y+1)}{ (1+a(x_{i}))} \right) \right) \\
e^{\hat{MSE}} = \exp\left(\frac{1}{l} \sum_{i=1}^{l}\left( 2\ln\frac{(y+1)}{ (1+a(x_{i}))} \right) \right)

\end{gather}
$$
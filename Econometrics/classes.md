## 15.09

№ 5
$$
TSS = \sum(y_{i}-\bar{y})^2 = \sum(\hat{y}_{i}-\bar{y})^2+\sum e_{i}^2
$$
$$
\begin{align}
TSS = ESS + RSS \\ 
(SST = SSE + SSR) \\
\end{align}
$$(Total SS, Explained SS, Residual SS)


№ 6
$R^2 = [corr(x;y)]^2 = [\hat{corr}(y;\hat{y})]^2$ 
Proof:
$$
\begin{align}
R^2 &= \frac{ESS}{TSS}= \frac{\sum(\hat{y_{i}}-\bar{y})^2}{\sum(y_{i}-\bar{y}^2)} = \frac{\sum{(\hat{\beta_{0}}+\hat{\beta_{1}}x_{i}-\bar{y})^2}}{\sum(y_{i}-\bar{y})^2}=\\
&= \hat{\beta_{1}}^2 - \frac{{\sum(x_{i}-\bar{x}^2)}}{\sum(y_{i}-\bar{y})^2}= \frac{{\left(\frac{1}{n}\sum(x_{i}-\bar{x})(y_{i}-\bar{y}) \right)^2}}{\frac{1}{n}\sum(x_{i}-\bar{x})^2 \cdot \left[ \sum(y_{i}-\bar{y})^2 \cdot \frac{1}{n}\right]}=\\
&= \frac{{\hat{cov}(x;y)^2}}{\hat{V}(x) \cdot\hat{V}(y)} = [corr(x;y)]^2
\end{align}
$$



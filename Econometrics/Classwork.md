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




## 18.01

![[Pasted image 20240118150655.png]]

(i)
$$
\begin{align}
\lvert\lvert \hat{u} \rvert\rvert _{2}^{2} \to \min_{\beta} \\
\lvert\lvert X\beta - Y \rvert\rvert^{2}_{2} \to \min_{} \\
 \\
\beta = \begin{bmatrix}
\beta_{1} \\
\beta_{2} \\
\beta_{3} \\
\dots
\end{bmatrix} \quad \quad X = \begin{bmatrix}
1 & x_{21} & x_{31} \\
\vdots  & \vdots  & \vdots   \\
1 & x_{2n} & x_{3n} 
\end{bmatrix} \\
Y = \begin{bmatrix}
Y_{1} \\
\dots \\
Y_{n}
\end{bmatrix} \quad u = \begin{bmatrix}
u_{1} \\
\dots \\
u_{n}
\end{bmatrix}
\end{align}
$$

![[Normal Equation for OLS]]

$$
\begin{align}
\bar{y} = b_{1}+b_{2}\bar{x}_{2}+b_{3}\bar{x}_{3} \implies \hat{b}_{1} = \bar{Y} - b_{2}\bar{X}_{2} - b_{3}\bar{X}_{3}\\
cov(X_{2}, Y) = \beta_{2}  \cdot  Var(X_{2}) + \beta_{3}Cov(X_{2},X_{3})\\
cov(X_{3},Y) = b_{2}Cov(X_{2},X_{3}) + b_{3}Var(X_{3}) 
\end{align}
$$
![[Cramer's Rule]]

$$
\begin{bmatrix}
Var(X_{2})  &  Cov(X_{2}, x_{3} )  & \mid Cov(X_{2},Y) \\
Cov(X_{2},X_{3}) & Var(X_{3})   & \mid Cov(X_{3}, Y)
\end{bmatrix}

$$
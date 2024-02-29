N1
[[System Of Simultaneous Equations]]
![[Pasted image 20240229144928.png]]
Solve system of equations
$$
\begin{cases}
c_{t} = \alpha_{1} + \alpha_{2} y_{t} + \alpha_{3}c_{t-1} + u_{1t} \\
i_{t} = b_{1} + b_{2}r_{t} + b_{3}y_{t} + u_{2t} \\
y_{t} = c_{t} + g_{t} + i_{t}
\end{cases}
$$

Exogenous: $r_{t}; g_{t}; c_{t-1}$ 

Order condition:
M - number of equations

excluded (собираем переменные которых нет в этом уравнении, *omitted variables*)
1: $i_{t};r_{t}; g_{t}$ > (M-1) = 2  - works
2: $c_{t}; c_{t-1}; g_{t}$ > (M-1) = 2 - works
3: all coefficients are known for 3rd equation (1, 1, 1), so we don't need to check
Satisfied, then have to check the rank condition

Rank condition:
1: 
$$
\begin{align}
\begin{matrix}
i_{t} & r_{t} & g_{t} \\
-1  & \beta_{2}  & 0 \\
1  & 0  & 1
\end{matrix} \quad  rank =2 = M-1
\end{align}
$$
2: 
$$
\begin{align}
\begin{matrix}
c_{t} & c_{t-1} & g_{t} \\
-1 & \alpha_{3} & 0
\end{matrix} \quad  rank=2 = M-1
\end{align}
$$
Satisfied => It is possible to estimate the coefficients

b) use [[2 Step Least Squares (2SLS)]] 


N2
![[Pasted image 20240229150317.png]]

$$
\begin{align}
Y_{i} \sim N(0,\sigma ^{2}) = \begin{cases}
N(0, \sigma^{2}_{s}) & summer \\
N(0, \sigma^{2}_{w}) & winter  
\end{cases} \\
n_{1}=50(summer) \to \sum y =10 \quad  \sum y^{2}=100 \\
n_{2}=50(winter) \to \sum y = -20 \quad  \sum y^{2} = 500 \\
H_{0} : \sigma_{s}^{2} = \sigma_{w}^{2} \quad  \text{with LM Test}
\end{align}
$$
[[Lagrange Multiplier (LM) Test]]
****
Calculate gradient, and 2nd derivatives. We evaluate gradient in point with constraints $\hat{\sigma^{2}} = a$
$$
\begin{align}
&\mathcal{L} = \prod_{i=1}^{50} \frac{1}{\sqrt{ 2\pi }\sqrt{ \sigma_{s}^{2} }} e^{-1/2  \cdot  y_{i}^{2}/\sigma_{s}^{2}}  \cdot  \prod_{i=51}^{100} \frac{1}{\sqrt{ 2\pi }\sqrt{ \sigma_{w}^{2} }}e^{-1/2  \cdot  y_{i}^{2}/\sigma^{2}_{w}} \\
&\ln \mathcal{L} = \sum_{i=1}^{50} \left( -\frac{1}{2}\ln_{2}\pi  -\frac{1}{2} \ln\sigma^{2}_{s} -\frac{\frac{1}{2}y_{i}^{2}}{\sigma^{2}_{s}}\right) + \sum_{i=51}^{100} \left( -\frac{1}{2} \ln 2\pi - \frac{1}{2}\ln \sigma_{w}^{2} - \frac{\frac{1}{2}y_{i}^{2}}{\sigma_{w}^{2}} \right) \to \max_{\sigma_{s}^{2}; \sigma^{2}_{w}}  \\
&\frac{ \partial \ln \mathcal{L} }{ \partial \sigma^{2}_{s} } = -\frac{n}{2}  \cdot \frac{1}{\sigma^{2}_{s}} + \frac{1}{2}\sum_{i=1}^{50} \frac{y_{i}^{2}}{\sigma_{s}^{2^{2}}} =0  \\
&\frac{ \partial \ln \mathcal{L} }{ \partial \sigma^{2}_{w} } = -\frac{n}{2}  \cdot \frac{1}{\sigma^{2}_{w}} + \frac{1}{2}\sum_{i=51}^{100} \frac{y_{i}^{2}}{\sigma_{w}^{2^{2}}} =0  \\ \\
&\frac{ \partial^{2} \ln \mathcal{L} }{ (\partial \sigma_{s}^{2})^{2} }  = \frac{n}{2}  \cdot  \frac{1}{(\sigma_{s}^{2})^{2}} - \sum_{i=1}^{50} \frac{y_{i}^{2}}{(\sigma_{s}^{2})^{3}}\\
&\frac{ \partial^{2} \ln \mathcal{L} }{ \partial \sigma_{s}^{2}\sigma_{w}^{2} } = 0 = \frac{\partial \ln \mathcal{L} }{\partial \sigma_{s}^{2} \partial \sigma_{w}^{2}}  \\ \\

&\text{Finally found point of constraints} \\
&\frac{ \partial^{2} \ln \mathcal{L} }{ (\partial \sigma_{w}^{2})^{2} }  = \frac{n}{2}  \cdot  \frac{1}{(\sigma_{w}^{2})^{2}} - \sum_{i=51}^{100} \frac{y_{i}^{2}}{(\sigma_{w}^{2})^{3}}  \\ \\

&\text{Equate the variances (Restricted)}  \\
&\ln \mathcal{L}_{R} = \sum_{i=1}^{100} \left( -\frac{1}{2}\ln 2\pi  - \frac{1}{2}\ln\sigma^{2} - \frac{1}{2} \frac{y_{i}^{2}}{\sigma^{2}}\right) \to \max_{\sigma^{2}}
\end{align}0
$$


$$
\begin{align}
&\frac{ \partial \ln \mathcal{L}_{R} }{ \partial \sigma^{2} }  = -\frac{n}{2} \frac{1}{\sigma^{2}} + \frac{1}{2} \sum \frac{y_{i}^{2}}{\sigma^{2^{2}}} = 0 \mid  \cdot  (\sigma^{2})^{2} \cdot 2 \\
&-n\sigma^{2} + \sum_{i=1}^{100}y_{i}^{2} = 0 \quad  \hat{\sigma^{2}} \frac{\sum_{i=1}^{100}y_{i}^{2}}{100} = 6 \\
&\frac{\partial^{2}\ln \mathcal{L}_{R} }{\partial\sigma^{2}} = \frac{n}{2} \frac{1}{\sigma^{2}}^{2} - \sum \frac{y_{i}^{2}}{(\sigma^{2})^{2}} < 0 \implies \max_{} \\ \\
&\text{Substitute sample variance} \\
&\frac{ \partial \ln \mathcal{L} }{ \partial \sigma^{2}_{s} } =  -\frac{200}{72} \\
&\frac{ \partial \ln \mathcal{L} }{ \partial \sigma^{2}_{w} } =  \frac{200}{72}
\end{align}
$$
$$
\begin{align}
 &\text{substitute values in our 2nd derivatives for point } \sigma^{2} = 6  \\
&\text{and evaluate expected value we get points (we did not count them fully):} \\
&\left\{ k_{1},k_{2},k_{3}  \right\} \\ \\

&\hat{I} = \begin{bmatrix}
k_{1}  & 0 \\
0  & k_{3}
\end{bmatrix} \\
&LM = \left( -\frac{200}{72} \quad \frac{200}{72} \right) \begin{bmatrix}
k_{1}  & 0 \\
0  & k_{3}
\end{bmatrix} \begin{bmatrix}
-\frac{200}{72} \\
\frac{200}{72}
\end{bmatrix} \text{ - is our test statistic}
\end{align}
$$
$\hat{I}$ - [[Fischer Matrix of Information]]
$$
LM \sim \chi^{2}_{j} \quad  j - \text{degree of freedom}
$$


N3 
![[Pasted image 20240229154729.png]]

![[Pasted image 20240229154736.png]]
$$
\begin{align}
\log \mathcal{L} = -15
\end{align}
$$
1) Coffee = 0. GPA=? for $ME_{GPA} \max_{}$. [[Marginal Effect (ME)]]
$$
\begin{align}
ME_{GPA} = \frac{ \partial P(Y=1) }{ \partial GPA } = \Lambda'(\dots)  \cdot  0.2 \to \max_{}  \\
-1 + 3 Coffee - 0.5Coffee^{2} + 0.2GPA =0\\
-1 + 0.2GPA = 0 \\
GPA^{*} = 5
\end{align}
$$

![[Pasted image 20240229155300.png]]
 2) $(3- Coffee)$ - производная по Coffee
$$
\begin{align}
ME_{Coff} = \frac{ \partial P(Y=1) }{ \partial Coff } = \underbrace{ \Lambda'(\dots) }_{ \neq 0 } (3-Coffee) = 0 \\
3 - Coffee = 0 \\
Coffee^{*} = 3
\end{align}
$$
![[Pasted image 20240229155611.png]]
3) $\log \mathcal{L}_{int} = -4$ - Unrestricted model (part 1)
 $\log \mathcal{L}_{boring}=-7$ - Unrestricted model (part 2)
 [[Likelihood Ratio (LR) Test]]
 $\log \mathcal{L}= -15$ - Restricted Model

4 - number of restrictions (number of coefficients in the equation)
$$
\begin{cases}
\beta_{0}^{i} = \beta_{0}^{b} \\
\beta_{c}^{i}= \beta_{c}^{b} \\
\beta_{c^{2}}^{i} = \beta_{c^{2}}^{b} \\
\beta_{GPA}^{i} = \beta_{GPA}^{b}
\end{cases} - \text{ 4 restrictions, setting D.O.F for the distribution}
$$
$$
LR = -2(\log \mathcal{L}_{R} - \log \mathcal{L}_{UR}) = -2 \cdot (-15-(-4-7)) = 8 \sim \chi^{2}_{4}
$$

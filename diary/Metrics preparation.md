![[Pasted image 20231225225415.png]]

a)
$$
\begin{align}
\hat{P}_{i} = 10000 + 90M_{i} + 2700A_{i} \\
\hat{P}_{i} = 10000 + 90  \cdot K_{i} / 1.6 +2700(1-T_{i})  \\
\hat{R}_{i} = \left(  10000 + 90  \cdot K_{i} / 1.6 +2700(1-T_{i}) \right)  \cdot  90 \\
\hat{R_{i}} = 1.143×10^6 + 5062.5 K_{i} - 243000 T_{i} \\ \\
\text{Check: ...........................................................} \\
M = 1, A = 0, P = 10090  \text{ in USD} \\
K_{i} = 1.6, T_{i}=1, R = 12700 + 56.25 -2700\cdot 1.6 = 10090  \cdot  90
\end{align}
$$


b) As all transformations to variables were linear, model can not lose it's ability to capture data structure, therefore $R_{1}= R_{2}$.


![[Pasted image 20231225232108.png]]
![[Pasted image 20231225232117.png]]

$$
\begin{align}
\hat{P}_{i} = \beta_{0} + \beta_{1}T_{i} + \beta_{2}W_{i}
\end{align}
$$
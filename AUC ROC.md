Area Under Curve: Receiver Operating Characteristic 

## FPR & TPR
$$
\underbrace{ FPR }_{ \begin{gather}
false  \\
positive \\
rate
\end{gather}} = \frac{FP}{FP+TN} = \frac{FP}{\ell_{-}}
$$
$$
TPR  = \frac{TP}{TP+FN} = \frac{TP}{\ell_{+}} = recall
$$
Перебираем все t, и для каждого оцениваем FRP и TRP.  Рисуем их на графике.


![[Pasted image 20231013121642.png|500]]

## Be careful
AUC-ROC может вводить в заблуждение, если есть много легко-различаемых объектов. 
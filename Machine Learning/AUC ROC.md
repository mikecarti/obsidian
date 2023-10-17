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

![[Pasted image 20231013122837.png]]

А [[PR-Curve (AUC-PRC)]] будет плохой - лучше учитывает дисбаланс.

# Association to Defective Pairs in Ranking
$$
DP = \frac{{2l_{-}l_{+}}}{l(l-1)} \cdot (1-AUCROC)
$$
## About models that are worse then random

![[Pasted image 20231017134157.png|450]]
$a(x)$
$AUCROC(a) < 0.5$

How to make it > 0.5?
$\tilde{a}(x) = -a(x)$

Note:
$TPR = \frac{RP}{l+}$
$FPR = \frac{FP}{l-}$

$$
\begin{gather}
TP(\tilde{a}) =FN(a) \\
FP(\tilde{a}) = TN(a) \\
TPR(\tilde{a}) = \frac{FN(a)}{l+} = 1 - TPR(a) \\
FPR(\tilde{a}) = 1 - FPR(a)
\end{gather}
$$


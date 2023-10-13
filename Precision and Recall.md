### Precision
насколько можно доверять модели если a(x)=+1   (точность)
$$
precision = \frac{TP}{TP+FP} 
$$

### Recall
насколько модель покрывает положительный класс (полнота)
$$
recall = \frac{TP}{TP+FN}
$$
Например если мы предсказываем болеет ли человек, нам важна полнота.

### How to balance between precision and recall?
$$
\begin{align}
a(x) &= sign\underbrace{ <w,x> }_{ \text{Prob(X - positive)} } \\
a(x) &= sign \;b(x)
\end{align}
$$
Sort by b(x):
![[Pasted image 20231013114111.png]]
Blue will yield high precision, low recall.
Red will yield low recall, high precision

Usually precision and recall is regulated by threshold choosing


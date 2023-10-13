### Precision
How much you can trust the model when: a(x)=+1   (точность)
$$
precision = \frac{TP}{TP+FP} 
$$

### Recall
How much model covers positive class (полнота)
$$
recall = \frac{TP}{TP+FN}
$$
For example if we predict, if person is ill or not, recall is more important, because we want to identify maximum ill people, even at the cost of identifying healthy people as ill.

### How to balance between precision and recall?
$$
\begin{align}
a(x) &= sign\underbrace{ <w,x> }_{ \text{Confidence(X: +1)} } \\
a(x) &= sign \;b(x)
\end{align}
$$
Sort by b(x):
![[Pasted image 20231013114111.png]]
Blue will yield high precision, low recall.
Red will yield low recall, high precision

Usually precision and recall is regulated by threshold choosing
So *after* model training we fix weights $w$ and find threshold $t$: 
$$
\begin{cases}
precision \to max \\
recall \geq 0.9
\end{cases}
$$

### [[F-Score]]



## Related:
[[Confusion Matrix]]
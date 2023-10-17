## 17.10

2)
$b(x) \in [0,1]$
On this interval, neg. objects are distributed with $pdf(b) = 2 - 2b$
pos. objects are distributed with $pdf(b) = 2b$

ROC - formula, area under it?


$[b(x)\geq t]$
$TPR(b, t)$
![[Pasted image 20231017135403.png|460]]

then 
$y = 2\sqrt{ x } - x$
$TRP = 2\sqrt{ FRP } - FRP$
$\int_{0}^{1} (2\sqrt{ x }-x) \, dx=\frac{5}{6}$


5)$l$ = 4000 (bank clients)
enough budget to only call 800 times
data analysts derived that 6% of clients respond on this invitation
data scientists made 2 models

$\mathcal{A}$: FPR = 0.1, TPR = 0.2
$\mathcal{B}$: FPR = 0.25, TPR = 0.6

We want to call 800 clients.
$800 = TPR \cdot l_{+} + FPR \cdot l_{-}$
$l_{+} = 4000 \cdot 0.06 = 240$
$l_{-} = 3760$
$\mathcal{A}: 0.2 \cdot 240 + 0.1 * 3760 = 424$
$\mathcal{B}: 1084$
$\mathcal{C}: x\to^{\alpha} \mathcal{A}(x)$
$\mathcal{C}: x \to^{1-a}\mathcal{B}(x)$
$TPR(C) = \alpha TPR(\mathcal{A}) + (1-\alpha)(TPR(\mathcal{B}))$
![[Pasted image 20231017140944.png|500]]
TPR = 353/275
FPR = 51/275
$\alpha \approx 0.43$

6)$l_{+}, l_{-}$ - даны
$ROC(\mathcal{A})$ не ниже $ROC(\mathcal{B})$ $\Leftarrow \Rightarrow$  $PR(\mathcal{A})$ не ниже $PR(\mathcal{B})$
я не буду переписывать доказательство...
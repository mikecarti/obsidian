$$
Gini = 2\text{AUC-ROC} - 1
$$
![[Pasted image 20231013122326.png]]

Улучшение относительно случайной модели.

### Definition
$$
H = \sum p(1-p)
$$

### [[Entropy (information theory)]] and Gini Index

![[Pasted image 20231111154349.png|500]]

## Example
p("successful hunt") = 0.3
p("not succ. hunt") = 0.7

shaman A: 
p("say: hunt will be successful") =0.3 
p("say: hunt will be not successful") =0.3

P("Wrong Prediction") = $0.3*0.7 + 0.7*0.3 = 0.42$

## Related:
[[AUC ROC]]

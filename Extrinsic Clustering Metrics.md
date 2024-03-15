$X$ - sample
$X = (x_{i},y_{i})^{l}_{i=1}$
$y_{i} \, \in \, \{ 1,..K \}$

Want to estimate clusterization quality by X


# How to compare metrics of different clustering algorithms
Here is a problem:
![[Pasted image 20240315155233.png|w50]]

1) We need to match clusters from X and clusters from a(x)
2) Number of clusters may be different in labeled data and a(x) output

## Methodology
- Lets add axioms
- Check these axioms on assessors (people, who label data) 
- find a metric, that suits our axioms


### Axioms / Requirements
1) [[Homogeneity]]
![[Pasted image 20240315160043.png]]

2) Recall
![[Pasted image 20240315160131.png]]

3) Rag-bag (Мешок с мусором) - Don't add noise to a cluster
![[Pasted image 20240315160509.png]]

4) Size vs Quantity
![[Pasted image 20240315160842.png]]

# Metric [[B Cubed]] fits for all axioms

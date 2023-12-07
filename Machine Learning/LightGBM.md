[[Gradient Boosting]] from Microsoft

## Gradient-based one-side sampling (GOSS)
A lot of objects have low shift $s_{i}$ then we should not do anything with them. So rank these shifts, and smallest objects are sampled (only some small shifts are taken). So training sample is decreased and training is faster.

## Exclusive Feature Bundling
Some combinations of features in objects are met exclusively. Use graph and estimate полная ракраска вершин. 

## Growth of a tree
Build an unbalanced tree, so every sub-tree would have approximately the same number of objects. Leaf-wise tree construction (GOOD)
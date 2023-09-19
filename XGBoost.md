aka "Extreme Gradient Boosting".
![[Pasted image 20230831125924.png|700]]
- Scalable, distributed [gradient-boosted](https://en.wikipedia.org/wiki/Gradient_boosting) decision tree (GBDT) machine learning library.
- Provides parallel tree boosting and is the leading machine learning library for [[Linear Regression |Regression]], classification, and ranking problems.
- Uses tree #pruning (an algorithm that cuts non-critical parts of a tree to decrease [[Over-fitting]])
- XGBoost offers regularization, which allows you to control overfitting by introducing L1/L2 penalties on the weights and biases of each tree.
- Another feature of XGBoost is its ability to handle sparse data sets using the weighted quantile sketch algorithm. This algorithm allows us to deal with non-zero entries in the feature matrix while retaining the same computational complexity as other algorithms like stochastic gradient descent.
- XGBoost also has a block structure for parallel learning. And uses cache-awareness (memory).
- XGBoost offers out-of-core computing capabilities using disk-based data structures instead of in-memory ones during the computation phase.
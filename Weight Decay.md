```python
from torch import optim
optimizer = optim.SGD(model.parameters(), lr=1e-3, weight_decay=1e-4)
```

- $0 < weight.decay <1$
- Adds penalty to loss function to discourage large weights and biases ([[Neural Network#About]])
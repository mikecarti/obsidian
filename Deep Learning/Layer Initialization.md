```python
import torch.nn as nn

layer = nn.Linear(64, 128)
nn.init.uniform_(layer.weight)
```

# Related:
[[Transfer Learning]]
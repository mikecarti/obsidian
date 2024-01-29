Top idea in nowadays [[Deep Learning]]
(Обучение с переносом знаний)

Taking [[Neural Network]], that was pretrained on some data. How to easily transfer this model for another task?

### If we have small data for our task
- Take model from other task
- Change last layer for layer with needed output shape
- Train only last layer

### If we have more data (100.000+)

![[Pasted image 20231019135924.png]]
- Freeze model to the middle
- Train other layers


# PyTorch Transfer Learning
```python
import torch

layer = nn.Linear(64,128)
torch.save(layer, 'layer.pth')

new_layer = torch.load('layer.pth')
```


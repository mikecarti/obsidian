- Should not be a symmetry (bad to init. weights with a single weights)
- A good idea:
- n - input shape for a layer (not exactly first layer)$$
\begin{align}
w_{j} \sim \frac{2}{\sqrt{ т }} \mathcal{N}(0,1)
\end{align}
$$
- trying to make scale of all layer outputs approximately equal

# PyTorch
```python
layer0 = nn.Linear(16, 32)
layer1 = nn.Linear(32, 64)

# Use uniform initialization for layer0 and layer1 weights
nn.init.uniform_(layer0.weight)
nn.init.uniform_(layer1.weight)

model = nn.Sequential(layer0, layer1)
```

### Useful model building essentials
```
torch.nn - all buildings for computational graphs
torch.nn.Parameter - learning parameters
torch.Module - The base class for all NN custom modules
torch.optim - this is where Gradient Descent optimizers live
def forward() - model output computation
torch.utils.data.Dataset - for more complex datasets

torch.autograd - computational graph
torch.Tensor - computational tensor node in computation graph
torch.nn.functional as F           # layers, activations and more
```


### Algebra
```python
ret = A.mm(B)       # matrix multiplication
ret = A.mv(x)       # matrix-vector multiplication
x = x.t()           # matrix transpose
```



###### [Learning rate scheduling](https://pytorch.org/tutorials/beginner/ptcheat.html#learning-rate-scheduling)
```python
scheduler = optim.X(optimizer,...)      # create lr scheduler
scheduler.step()                        # update lr after optimizer upd. weights
optim.lr_scheduler.X                    # where X is ...

# ...LambdaLR, MultiplicativeLR,
# StepLR, MultiStepLR, ExponentialLR,
# CosineAnnealingLR, ReduceLROnPlateau, CyclicLR,
# OneCycleLR, CosineAnnealingWarmRestarts,
```

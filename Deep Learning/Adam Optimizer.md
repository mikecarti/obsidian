
Combines [[RMSProp]] and [[AdaGrad (Adaptive Gradient)]]

Also can be described as:
Exponential fading out from RMSProp (Exponential Momentum) &&
&& Adaptive Learning Rate for every parameter (based on learning rate history)

 [[Adam Optimizer]] uses both first and second moments. Contrary to [[RMSProp]], that uses only first moment.

# AdamW 
[Fixing Weight Decay Regularization in Adam](https://arxiv.org/abs/1711.05101)

Adding [[Weight Decay]] and moving averages of the [[Gradient]] (and its square) keep track of gradients of the [[Loss Function]] and also of the [[Regularization in DL|Regularization]] term.
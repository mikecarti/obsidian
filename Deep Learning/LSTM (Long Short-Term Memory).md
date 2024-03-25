**The modification of [[RNN (Recurrent Neural Network)]].**
![[Pasted image 20240325174256.png]]

## Motivation:
[[RNN (Recurrent Neural Network)]] explode or vanish their gradients because for long context multiplications of weights provide extremely close to 0 or close to infinite numbers.

## More info: 
https://youtu.be/YCzL96nL7j0?t=358


![[Pasted image 20231116135520.png]]




Square brackets - concatenation.
As in [[History of CNN#ResNet (2015) Deep Residual Learning for Image Recognition|ResNet]] we add pure $h_{t-1}$ multiplied by inertia coefficient $(1-z_{t})$ that was not multiplied by $W$. So we throw our old $h$ vectors on longer distances.

Better context length.


## Bidirectional LSTM

![[Pasted image 20231116140025.png]]

This model reads text from left-to-right and then from right-to-left. 
Uses all context.

## Related:
[[Seq2Seq]]
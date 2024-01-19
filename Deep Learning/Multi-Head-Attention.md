Improvement on [[Attention Mechanism]]

We will do everything from [[Attention is All You Need! (2017)]] but in *parallel*, 8 times.

Train 8 weights for k, v, q. Concatenate all attentions. So different heads can focus on their own special ideas. Just like with many filters in [[Convolutional Neural Network]]
![[Pasted image 20231207132716.png]]

![[Pasted image 20231207133002.png]]


## Scaled Dot-Product Attention

```image-layout-a
![[Pasted image 20240119160259.png]]
![[Pasted image 20240119160334.png]]
```



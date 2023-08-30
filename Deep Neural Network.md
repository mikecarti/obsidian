### Types:
- Usual simple Deep NN
- [[Liquid Neural Networks]]

## About
Neural nets is a oversimplified model of humans' brains. It consists of neurons. 
These neurons have their own trainable weights. 

![[Pasted image 20230811122542.png]]

W<sub>i,j</sub> = Weight from neuron i<sup>[n-1]</sup> to j<sup>[n]</sup> 
x1...xm =  Inputs
b<sub>i</sub><sup>[n]</sup> = [[Bias]] for i-th neuron on n-th layer
a<sub>i</sub><sup>[n]</sup> = R(X) = R(x<sub>1</sub> * w<sub>1</sub> + ... + x<sub>m</sub> * w<sub>m</sub> + b)
R = [[Activation  functions|Activation function]]
S = [[Sigmoid]] Function

$W_{i,j}=\text{ Weight from neuron } i^{[n-1]} \text{ to } j^{[n]}$
$x_{1} , \dots , x_{m} = \text{inputs}$
$b_{i}^[n]$ = [[Bias]] for i-th neuron on n-th layer
$a_{i}^{[n]}=R(X)=R(x_{1}*w_{1} + \dots + x_{m} * w_{m}+b$
R = 


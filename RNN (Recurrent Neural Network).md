![[Pasted image 20231116131844.png]]

$$
h_{t} = f (W_{xh}x_{t}) + W_{hh}h_{t-1}
$$
$W_{xh}$, $W_{hh}$, $W_{ho}$ - Matrices of correct size that transform vector to vector
f - non-linear function ([[RELU (Rectified Linear Unit)]], [[Sigmoid]])

- Typical: $o_{t}\, \in \,\mathbb{R}^{n}$
- $N$ - dictionary size (for example for words)
- So we predict probabilities for next word
- Predict the next word

Also may be used for [[POS tagging]]
- Typical: $o_{t}\, \in \,\mathbb{R}^{n}$
- $N$ - number of parts of speech (существительное, прилагательное, ...)
- [[POS tagging]]

## Architecture
![[Pasted image 20231116132335.png]]

![[Pasted image 20231116132427.png]]


## Multi-Layer RNN
![[Pasted image 20231116132751.png]]



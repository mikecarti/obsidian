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

During inference 
$$
x_{n+1} = h_{n}
$$
And we can measure the loss by:
$$
L(y_{i},o_{i})
$$
Where $y_{i}$ is the ground truth.

![[Pasted image 20231116132427.png]]


## Multi-Layer RNN
![[Pasted image 20231116132751.png]]


## Backprop
![[Pasted image 20231116134919.png]]

### As long ago weights are being lost, our weights and inference on long sequences is worse

Solution to this:
[[LSTM (Long Short-Term Memory)]]
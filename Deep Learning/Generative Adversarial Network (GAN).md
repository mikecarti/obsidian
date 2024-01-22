[Source](https://neptune.ai/blog/gan-loss-functions)

## In simple words
- Two Neural Networks are involved.
- One of the networks, the Generator, starts off with a random data distribution and tries to replicate a particular type of distribution.
- The other network, the Discriminator, through subsequent training, gets better at classifying a forged distribution from a real one.
- Both of these networks play a min-max game where one is trying to outsmart the other.

## Standard GAN [[Loss Function]]
$$
E_{x}\left[ \log(D(x)) \right] +E_{z}\left[ \log(1-D(G(z))) \right] 
$$
Generator tries to minimize this function, and Discriminator tries to maximize.

## Discriminator Loss
Discriminator during training classifies real data and fake data from the generator. When discriminator makes an error, penalty is paid.

$$
\nabla_{\theta_{d}} \frac{1}{m} \sum_{i=1}^{m}\left[ \log D(x^{(i)})+ \log \left( 1-D(G(z^{(i)})) \right)  \right] 
$$
- $\log(D(x))$ refers to probability that discriminator is rightly classifying the real image.
- $\log(1-D(G(z)))\to \max_{}$   helps to correctly label fake images.

## Generator Loss
While training, the random noise is sampled (do not confuse with a [[White Noise]]). And output is produced from that noise by a generator. Loss function evaluates based on classification result of a discriminator.
$$
\nabla_{\theta_{g}} \frac{1}{m}\sum_{i=1}^{m} \log \Big(1-D(G(z^{(i)})) \Big) \to \min_{}
$$


### Not saturating loss 
Saturation can prevent generator from training, if a descriminator trained way ahead of generator. 
$$
\log\Big(D(G(z))\Big)
$$
## Problems

### Mode Collapse
Model can only generate a small subset of different outcomes (modes).
<img src="https://i0.wp.com/neptune.ai/wp-content/uploads/2022/10/GAN-face-generator.png?ssl=1">



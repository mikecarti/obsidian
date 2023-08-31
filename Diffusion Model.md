Fundamentally, Diffusion Models work by **destroying training data** through the successive addition of Gaussian noise, and then **learning to recover** the data by _reversing_ this noising process. After training, we can use the Diffusion Model to generate data by simply **passing randomly sampled noise through the learned denoising process**.
![[Pasted image 20230831224711.png| 500]]

More specifically, a Diffusion Model is a [[Latent Variable]]model which maps to the [[Latent Space]] using a fixed Markov chain. This chain gradually adds noise to the data in order to obtain the approximate posterior

$$
q(x_{1}:T|x_{0}) 
$$
$\text{where } x_{1}, \dots , x_{T}$  are the [[Latent Variable | latent variables]] with the same dimensionality as $x_{0}$. In the figure below, we see such a Markov chain manifested for image data.
![[Pasted image 20230831230505.png]]
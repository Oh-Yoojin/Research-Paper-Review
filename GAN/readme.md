# Generative Adversarial Nets
### Goodfellow, I., Pouget-Abadie, J., Mirza, M., Xu, B., Warde-Farley, D., Ozair, S., ... & Bengio, Y. (2014). Generative adversarial nets. In Advances in neural information processing systems (pp. 2672-2680).

> __Generator model 𝐺__ that captures the data distribution 𝑝<sub>𝑧</sub>(𝑧).</br> __Discriminative model 𝐷__ that estimates the probability that a sample came from the training data rather than 𝐺.

##### Adversarial Training

![adversarial_net](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/GAN/img/dversarial_Training.png)

##### Theoretical Results

![distribution](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/GAN/img/distribution.png)

(_G_, green, solid line) : Generative distribution
(_D_, blue, dashed line) : Discriminative distribution
(black, dotted line) : Generating distribution
_x_, _z_ : part of the domain

The upward arrows show how the mapping _x = G(z)_ imposes the non-uniform distrbution _p<sub>g</sub>_ on transformed samples.

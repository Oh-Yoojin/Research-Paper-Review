# Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks
### Zhu, J. Y., Park, T., Isola, P., & Efros, A. A. (2017). Unpaired image-to-image translation using cycle-consistent adversarial networks. In Proceedings of the IEEE international conference on computer vision (pp. 2223-2232).

Image-to-image translation is a class of vision and graphics problems where the goal is to learn the mapping between an input image and an output image using a training set of aligned image pairs.
However, for many tasks, paired training data will not be available.

![result01](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/result01.png)

Given any two unordered image collections X and Y , our algorithm learns to automatically “translate” an image from one into the other and vice versa.

![training_data](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/training_data.png)

- left : paired training data
- right : unpaired training data

> Related work : [Generative Adversarial Nets](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/GAN/readme.md)

##### Formulation
###### Cycle consistency

![mapping_function](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/mapping_funtions.png)

###### Cycle loss function

![aim_to_solve](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/aim_to_solve.png)

![loss_function](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/cycle_loss_funtions.png)

##### Evaluation

![AMT](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/AMT_score.png)

![FCN](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/FCN_score.png)

##### Results

[![result02](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Generative%20Model/CycleGAN/img/result02.png)](https://youtu.be/9reHvktowLY)
> with sample video


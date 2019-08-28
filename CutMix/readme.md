# CutMix: Regularization Strategy to Train Strong Classifiers with Localizable Features
### Yun, S., Han, D., Oh, S. J., Chun, S., Choe, J., & Yoo, Y. (2019). Cutmix: Regularization strategy to train strong classifiers with localizable features. arXiv preprint arXiv:1905.04899.

__CutMix__ augmentation strategy : Patches are cut and pasted among training images where the ground truth labels are also mixed proportionally to the area of the patches.

To prevent a CNN from focusing too much on a small set of intermediate activations or on a small region on input images, random feature removal regularizations have been proposed(ex. dropout).
Entire dropout strategies improves generalization and localization by letting a model attend not only to the most discriminative parts of objects. While, regional dropout strategies have shown improvements of classification and localization performances to a certain degree, deleted regions are usually zeroed-out or filled with random noise, greatly reducing the proportion of informative pixels on training images.

![table](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/CutMix/img/compare_table.png)

##### Mixup
CutMix shares similarity with Mixup in that both __combines two samples__, where the ground truth label of the new sample is given by the mixture of one-hot labels.
Mixup performs feature-level interpolation and other types of transformations.

##### CutMix

The goal of CutMix is to generate a new training sample $(\tilde{x},\tilde{y})$ by combining two training samples $(x_{A},y_{A})$ and $(x_{B},y_{B})$.
$$\tilde{x} = M \odot x_{A} + (1 - M) \odot x_{B} $$
$$\tilde{y} = \lambda y_{A} + (1 - \lambda)y_{B} $$

Where $M \in {0,1}^{W \times H}$ denotes a binary mask indicating where to drop out and fill in from two images. $\odot$ is element-wise multiplication.

In this paper, sampling the rectangular masks $M$ whose aspect ratio is proportional to the original image.

To sample the binary mask $M$, first sample the bounding box coordinates $B = (r_{x}, r_{y}, r_{w}, r_{h})$ indicating the cropping regions on $x_{A}, x_{B}$. The region $B$ in $x_{A}$ is dropped out and filled with the patch cropped at $B$ of $x_{B}$.

![dog_example](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/CutMix/img/dog_ex.png)

##### Result
![result_01](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/CutMix/img/result_01.png)

## EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks
### Tan, M., & Le, Q. V. (2019). EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks. arXiv preprint arXiv:1905.11946.

##### In EfficientNet, rethinking all scaling of CNN to prove the accuracy and the efficiency.

##### Compound Model Scaling: A Better Way to Scale Up CNNs
In order to understand the effect of scaling the network, It is important to study the impact of scaling different dimensions of the model.

![scaling methods](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/EfficientNet/img/scaling.png)

The first compound scaling method is to perform a grid search to find the relationship between different scaling dimensions of the baseline network under a fixed resource constraint.
This determines the appropriate scaling coefficient for each of the dimensions mentioned above.

##### Problem Formulation
Maximize the model accuracy for any given resource constraints, which can be formulated as an optimization problem.

![Problem Formulation](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/EfficientNet/img/function.png)

_w, d, r_ are coefficients for scaling network width, depth, and resolution.

> __Observation 1__ : Scaling up any dimension of network width, depth, or resolution improves accuracy, but the accuracy gain diminishes for bigger models.

##### Compound Scaling Method
Different scaling dimensions are not independent. For higher resolution images, should be increased network depth. So increase the network width when resolution is higher

![Compound scaling method](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/EfficientNet/img/compund.png)

New compound scaling method uses a compound coefficient _φ_ to uniformly scales network width, depth, and resolution in a principled way.

> __Observation 2__ : In order to pursue better accuracy and efficiency, it is critical to balance all dimensions of network width, depth, and resolution during ConvNet scaling.

##### EfficientNet Architecture
![structure](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/EfficientNet/img/structure.png)
<sub> Refer to [ai.googleblog](https://ai.googleblog.com/) <sub/>

EfficientNet architecture uses mobile inverted bottleneck convolution(MBConv). It is similar to MobileNetV2 and MnasNet, but it is slightly larger due to an increased FLOP budget.

## AlignedReID: Surpassing Human-Level Performance in Person Re-Identification
### Zhang, X., Luo, H., Fan, X., Xiang, W., Sun, Y., Xiao, Q., ... & Sun, J. (2017). Alignedreid: Surpassing human-level performance in person re-identification. arXiv preprint arXiv:1711.08184.

##### AlignedReID
![AlignedReID](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Re-Identification/AlignedReID/img/AlignedReID_model.png)

In this model, generate a single global feature as the final output of the input image, and use the L2 distance as the similarity metric. (global feature is learned jointly with local features in the learning stage.)

For each image, extract a feature map with ResNet50, (_C × H × W_, where _C_ is the channel number and _H × W_ is the spatial size, 2048 × 7 × 7).

- __global feature__ (a _C-d_ vector) is extracted by directly applying global pooling on the feature map.

- __local features__, a horizontal pooling, which is a global pooling in the horizontal direction, is first applied to extract a local feature for each row, and a 1 × 1 convolution is then applied to reduce the channel number from _C_ to _c_.

In this way, each local feature (a _c-d_ vector) represents a horizontal part of the image for a person.

As a result, __a person image is represented by a global feature and _H_ local features__.

The __distance__ of two person images is the __summation of their global and local distances__.

![AlignedReID_01](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Re-Identification/AlignedReID/img/AlignedReID_01.png)

- Global distance : L2 distance of the global features
- Local distance : matched the local parts from top to bottom to find the alignment of local features with the minimum total distance


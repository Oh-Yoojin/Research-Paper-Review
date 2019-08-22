## Beyond Part Models: Person Retrieval with Refined Part Pooling (and A Strong Convolutional Baseline)
### Sun, Y., Zheng, L., Yang, Y., Tian, Q., & Wang, S. (2018). Beyond part models: Person retrieval with refined part pooling (and a strong convolutional baseline). In Proceedings of the European Conference on Computer Vision (ECCV) (pp. 480-496).

##### PCB: A Strong Convolutional Baseline
###### Structure of PCB

![pcb_structure](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Re-Identification/PCB_RPP/img/PCB_structure.png)

Backbone network without hidden fully-connected layers designed for image classification as the backbone.

 - In this paper, mainly employs ResNet50

Original global average pooling(GAP) layer is maintained exactly the same as the backbone model. This is the differences in PCB model GAP.

In this paper, defined the vector of activations viewed along the channel axis as a column vector.

PCB partitions _T_ into _p_ horizontal stripes and averages all the column vectors in a same stripe into a single part-level column vector _g<sub>i<sub/>_ (_i_ = 1, 2, · · · , _p_). Afterwards, PCB employs a convolutional layer to reduce the dimension of _g_ and then _h_ are set to 256-dim.  Finally each classifier is implemented with a fully-connected (FC) layer and a sequential Softmax layer.


###### Refined Part Pooling

![RPP](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/Re-Identification/PCB_RPP/img/RPP.png)

In this part, focusing on the tensor T to be spatially partitioned.

After training PCB to convergence, compareing the similarities between each _f_ and _g<i (_i_ = 1, 2, · · · , _p_), _i.e._, the average-pooled column vector of each stripe, by measuring cosine distance. If _f_ is closest to _g<sub>i<sub/>_, _f_ is inferred as closest to the _i<sub>th<sub/>_ part.

As a result, It is possible to find the closest part to each _f_. Each column vector is denoted by a small rectangle and painted in the color of its closest part.


###### Induced training for part classification
> __Step 1.__ A standard PCB is trained to convergence with
uniform partition.

> __Step 2.__ A p-category part classifier is appended on the
tensor _T_.

> __Step 3.__ All the pre-trained layers of PCB are fixed.
Only the part classifier is trainable. The model is trained until convergence again.

> __Step 4.__ The whole net is fine-tuned to convergence for
overall optimization.

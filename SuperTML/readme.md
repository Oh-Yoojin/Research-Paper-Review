# SuperTML: Two-Dimensional Word Embedding for the Precognition on Structured Tabular Data.
### Sun, B., Yang, L., Zhang, W., Lin, M., Dong, P., Young, C., & Dong, J. (2019). SuperTML: Two-Dimensional Word Embedding for the Precognition on Structured Tabular Data. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition Workshops (pp. 0-0).


> Super __TML__ (__T__ abular data __M__ achine __L__ earning) :  __Two-Dimensional__ Word __Embedding__ for the
Precognition on __Structured Tabular Data__

Tabular data is the most commonly used form of data in industry according to a Kaggle ML and DS Survey.
But all attempts have used one-dimensional embeddings.

In this paper, propose the __SuperTML method__, which borrows the idea of __Super Characters method__ and __two-dimensional embeddings__ to address the problem of classification on tabular data.

##### SuperTML Method
The Super Characters method is a two-step method that was initially designed for text classification problems.

![superTML](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/SuperTML/img/superTML_ex.png)

- __First Step__ : Two-dimensional embedding. Input(tabular) features are projected onto a two-dimensional embedding.

> This is an example with iris data table.</br>
![iris_table](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/SuperTML/img/iris_table.png)</br>
Embedding the iris data to superTML images.</br>
![embedding](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/SuperTML/img/embedded_iris01.png)

- __Second Step__ : Using pretrained CNN models to fine-tune on the generated SuperTML images.

> Transfer Learning</br>
![Transfer_learning](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/SuperTML/img/transfer_learning.png)</br>
refer to : [O'REILLY](https://www.oreilly.com/library/view/java-deep-learning/9781788997454/de1d99a5-576d-45de-b77f-ee5563550894.xhtml), [SSinyu](https://github.com/SSinyu)

Considering that features may have different importance for the classification task, it would be prudent to allocate larger spaces for important features and increase the font size of the corresponding feature values. So, SuperTML is designed 2 kinds of algorithm.

![VF_n_EF](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/SuperTML/img/VF_n_EF.png)

- __SuperTML VF__: SuperTML method with Variant Font size for embedding.
> 1 : Calculate the feature importance in the given tabular data provided by other machine learning methods.</br>
2 : Design the location and font size of each feature in order to occupy the image size as much as possible.(Make sure no overlapping among features.)</br>
3 : Same as SuperTML step

- __SuperTML EF__: SuperTML method with Equal Font size for embedding
> 1 : Draw the feature in the same font size without overlapping, such that the total features of the sample will occupy the image size as much as possible.</br>
2 : Same as SuperTML step

##### Result
![result01](https://github.com/Oh-Yoojin/Research-Paper-Review/blob/master/SuperTML/img/result01.png)

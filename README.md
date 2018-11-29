# zero-shot-learning guidebook
In order to familiarize more people with zero-shot-learning, we create the reposiyory to introduce some basic knowledge about it.
## What is zeor-shot-learning?

In the convolutional classfication model, we need a large number of data to train the model. So when we categorize a new class, we have to collect data again. And because of the changes in nature and the emergence of new species, it is becoming more and more difficult to identify species only by collecting data. 
![](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/1.png)

In order to resolve such problem, Lampert proposed a classic attribute-based approach called zero-shot-learning which has ability to tansfer knowledge without collecting new data. It is also the same way that humans preview new things.Let's take a look at its structure.


![pic-1](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/3.png)

![pic-1](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/2.png)

As we can see from the structure, zero-shot-learning includes seen class、model、side information and unsenn class. Seen class and unseen class are disjoint. We use the seen data to get the visiual feature. Usually we utilize deep learning to get the feature. Side information mainly includes the  attributes of class and label. For example, we can use fat, big ears,big nose to descripe a pig. Unseen data is the source that we hope to predict directly. Finally we hope get a suitable model that maps visiual feature to the side information and use the side information to predict the unseen class.
   
## Take a close look at it
 - Framework of the method
![pic-1](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/4.png)
 - Seen data and Unseen data
 Seen data are the source that we train to get the visiual feature. We hope to get signifant information from the seen data and transfer it to the unseen data. On account of the unseen data are disjoint with seen data, so we need to utilize side information to predict the label.
 
 - Visiual Feature
 



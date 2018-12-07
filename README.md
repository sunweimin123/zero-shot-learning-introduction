# zero-shot-learning guidebook
In order to familiarize more people with zero-shot-learning, we create the reposiyory to 
introduce some basic knowledge about it.
## What is zeor-shot-learning?

In the convolutional classfication model, we need a large number of data to train the model. 
So when we categorize a new class, we have to collect data again. And because of the changes 
in nature and the emergence of new species, it is becoming more and more difficult to identify 
species only by collecting data. 
fig1:![pic-1](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/1.png)

In order to resolve such problem, Lampert proposed a classic attribute-based approach called 
zero-shot-learning which has ability to tansfer knowledge without collecting new data. It is 
also the same way that humans preview new things.Let's take a look at its structure.


![pic-2](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/2.png)

As we can see from the structure, zero-shot-learning includes seen class、model、side information 
and unsenn class. Seen class and unseen class are disjoint. We use the seen data to get the visiual 
feature. Usually we utilize deep learning to get the feature. Side information mainly includes the  
attributes of class and label. For example, we can use fat, big ears,big nose to descripe a pig. 
Unseen data is the source that we hope to predict directly. Finally we hope get a suitable model 
that maps visiual feature to the side information and use the side information to predict the 
unseen class.
   
## Generalized zero-shot learning(GZSL)
 - Introduction
 
 Zero-shot learning has been proven to be a great way to
 resolve the problem that learning with no data. 
 Nevertheless, it only applies when there is no seen classes
 in testing. So when we apply such method to the real
 situation, it does not work very well. In order to
 resolve such problem, we propose GZSL to recognize 
 any test instance coming either from a known
 class or from a novel class that has no training
 instance.
 
 
![pic-3](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/4.png)

 - Method
 
 Previous methods concentrate on more additional side information.In this paper, we mine the hidden 
 relationship of classes.Although test instances can be classified through computing the nearest 
 neighbor between the mapped features and the original class attributes, it’s not effective just 
 using the assistance of semantic attributes to build feature mapping. We introduce dissimilarity 
 representation as a new transformed feature for instances.As shown in the figure below, 
 visiual features of class are projected into the attribute space. We get the dissimilarity 
 representation respectively from attribute space and visiual space.Here, with the assistance of 
 dissimilarity representation, we propose an efficient feature mapping method, named Dissimilarity 
 Representation Learning (DSS). According to the mapping complexity, DSS is divided into shallow 
 mapping(DSSs) and deep mapping (DSSd).

  ![pic-4](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/5.png)

 
 - Shallow Mapping Dissimilarity Representation Learning(DSSs)
 
 The core of this method is to use seen classes as reference points. Algorithm 1 shows the 
 shallow mapping of DSS (DSSs). Steps are as follows.
 
 1.Calculate the average values of class attributes and visiual features as reference points.
 
 2.Calculate the dissimilarity values in attribute space and visual space respectively.
 
 3.Comparing the difference between attribute space and visual space to predict the class.
 
 ![pic-5](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/6.png)
 
 DSSs is efficient on the GZSL problem for its no need of learning, but there are certainly 
 existing projection domain shift and deviation.
 
 - Deep Mapping Dissimilarity Representation Learning(DSSd)
 
 In order to resolve the problem of projection domain shift, DSSd adopt an available mappings to
 generate the key instances of unseen classes.In DSSd, a two-level mapping neural network with domain
 adaptions is constructed, shown in the below.
 
 ![pic-6](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/8.png)
 
 The two-level mapping has two different objective functions to minimize the regression loss. 
 
 ![pic-7](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/10.png)
 
 The first one is related to the feature mapping in the attribute space. sim() calculates the similarity
 between f() and a. f() represents the mappings from visiual space to attribute space. the second 
 term confirms a discriminable mapping, and the third term increases the robustness of projection. 
 Notably, g1(f ,W ) instructs the feature mapping from the visual space to the attribute space 
 to be more reasonable
 
 ![pic-8](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/11.png)
 
 The second one builds a projection from the attribute space to the dissimilarity space, just like
 the first term. After training on seen classes, utilizing the side information and the key instances
  of seen classes, a linear domain adaption is learned. Then we adopt the linear domain adaption to 
  the unseen class to get the key instace. Deep mapping of DSS (DSSd) is shown in Algorithm 2
 
 ![pic-9](https://github.com/sunweimin123/zero-shot-learning-introduction/blob/master/9.png)
 

 


---
title: "Machine Learning Gems"
description: "Nuggets of knowledge necessary for ML"
publishDate: 2022-11-22
image: "/assets/images/posts/machinelearning.jpg"
imageWidth: 500
imageHeight: 300
tags: ["Faqs", "Machine Learning", "Math"]
---

### What is the curse of dimensionality?

As the number of dimensions (features) in a dataset increases, the volume of the space increases exponentially. This requires exponentially more data points to maintain the same density, making statistical analysis and machine learning more challenging. High-dimensional data often leads to overfitting and computational complexity issues.

### What is the law of large numbers?

The Law of Large Numbers states that as the sample size increases, the sample mean approaches the population mean. In other words, with a large enough sample, the observed average will be close to the expected value. This is fundamental to statistical inference and probability theory.

### What is MLE?

Maximum Likelihood Estimation (MLE) is a method for estimating the parameters of a statistical model. It works by finding the parameter values that maximize the likelihood function, which measures how likely the observed data would be under different parameter settings. MLE is widely used in statistical modeling and machine learning.

### How do you define eigenvectors and eigenvalues?

An eigenvector of a linear transformation is a non-zero vector that changes only in scale (not direction) when that linear transformation is applied to it. The scalar factor by which the eigenvector is scaled is the eigenvalue. Mathematically, if A is a square matrix, v is an eigenvector, and λ is the corresponding eigenvalue, then: Av = λv.

### Discuss the curse of dimensionality in detail?

The curse of dimensionality refers to various phenomena that arise when analyzing data in high-dimensional spaces that do not occur in low-dimensional spaces. As dimensions increase:

1. The volume of the space increases exponentially, requiring exponentially more data points
2. Distance metrics become less meaningful as points tend to be equidistant from each other
3. Data becomes sparse, making it harder to find patterns
4. Computational complexity increases dramatically
5. Risk of overfitting increases

These issues impact machine learning algorithms, especially those that rely on distance calculations or require sufficient data density.

### What is deep Metric learning?

Deep Metric learning is a group of techniques used to measure the similarity of different data samples. The goal of metric learning is to learn a representation that maps objects into embedding space. The distance in the embedded space should preserve the objects' similarity. Contrastive loss and triplet loss are two popular loss functions.

Deep metric learning typically uses neural networks to create embeddings where semantically similar objects are close to each other and dissimilar objects are far apart. This is particularly useful for face recognition, image retrieval, and recommendation systems.


### What is contrasive loss ?

The idea of contrasive loss is to design a loss function that pulls the representations (of images for example) close together for similar images and push them apart the dissimilar images

### What is datacentric AI


### What is sensitivity ?


### What is AUC, ROC ?

Area under the curve and Receiver operating characteristic curve are two metrics used to evaluate the performance of binary classification models.

### What is specificity ?


### What is the intution behing MobileNets
The big idea behind mobilenets is to use the depthwise seperable convolutions to build light weight deep neural networks. https://machinethink.net/blog/googles-mobile-net-architecture-on-iphone/

### What are heuristics ?
Heuristics are mental shortcuts that can facilitate problem-solving and probability judgements. These strategies are generalizations or rules of thumb, reduce cognitive load and can be effective for making immediate judgements, however, they often result in irrational or inaccurate conclusions.

### What is cross validation ?
Cross validation is a method of model evaluation which splits the data in creative ways in order to obtain better estimates of "real world"
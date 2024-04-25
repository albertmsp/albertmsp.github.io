---
layout: post
title:  "Fastai model evaluation"
date:   2024-04-25 14:30:30 +0800
categories: jekyll update
---
There are many ways for us to evaluate the deep learning model, for the fastai models, there are two ways: confusion matrix and t_SNE

For confusion matrix:
Confusion matrix is a tool often used in classification to visualize the performance of an algorithm. Each row of the matrix represents the instances in an actual class, while each column represents the instances in a predicted class. This allows you to see where the model might be confusing two classes and is useful for identifying misclassifications.
![Image of confusion matrix](images/confusion)
For t_SNE:
t-SNE (t-distributed Stochastic Neighbor Embedding) is a machine learning algorithm for visualization developed by Laurens van der Maaten and Geoffrey Hinton. It reduces high-dimensional data to two or three dimensions so that it can be plotted on a graph. This technique is particularly good at creating a map that reveals structures at many different scales, which is crucial for understanding complex datasets with many variables.
![Image of confusion matrix](images/t_SNE.png)

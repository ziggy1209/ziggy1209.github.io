# Inception Network

Originally used in computer vision tasks, Inception network V1 topped in the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) 2014. In this post, we will mainly talk about Inception network V3, which improved the accuracy and reduced the architecture complexity of V1, and [its reduced version](https://github.com/google-research/google-research/blob/master/kws_streaming/models/inception.py), which has been used by Google to solve keyword spotting (KWS) problems.

## Background

> Until 2014, standard CNN structure is stacked convolutional layers, maybe max-pooling, then one or more fully-connected layers. This has limits: 
> - Large memory footprint
> - Large computation demand
> - Prone to overfitting
> - Vanishing and exploding gradients
> 
> For example, AlexNet has about 60 millison parameters.

To solve the aforementioned problems, [Inception module](https://arxiv.org/abs/1409.4842) which moves from fully connected to sparsely connected architectures (even inside the convolution) has been proposed. Based on a neuroscientific theory called Hebbian principle - neurons that fire together, wire together - meaning that when activity in one cell repeatedly elicits action potentials in a second cell, synaptic strength is potentiated, [the work of Arora et al.](https://arxiv.org/pdf/1310.6343.pdf) stated that 
> If the probability distribution of the dataset is representable by a large, very sparse deep neural network, then the optimal network topology can be constructed layer by layer by analyzing the correlation statistics of the activations of the last layer and clustering neurons with highly correlated outputs. 

Therefore, knowing that dense connections are expensive, that non-uniform sparse matrix calculations are expensive, while dense calculations are very efficient, the main idea of the Inception architecture is based on finding out how an optimal local sparse structure in a convolutional vision network can be approximated and covered by readily available dense components. 

A naive version of Inception module which approximates an optimal local sparse structure is illustrated as follows:

It 




## Inception Network V1


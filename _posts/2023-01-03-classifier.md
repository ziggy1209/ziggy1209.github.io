# Classifier and Loss Function

As the name suggests, what a classifier does is classifying data into different categories. In a deep neural network,
a classifier usually refers to the last/output layer of the whole network. You can choose the classifier according to 
your desired output - indices or probabilities.

A loss function quantifies the differnce between the desired output and the actual output of a neural network. When the
network is handling some classification task, the choice of loss function and how the loss function is applied is usually correlated with the classifier used.

In this post, we will review some popular loss functions and classifiers frequently used in classification task.

## Classifiers

There's no specific regulation about the choice of classifier - you can use a convolution block, or a simple linearizer, as 
far as it outputs the logits with desired shape.

## Loss functions

The choice of loss function is densely related to that of the classifier - if the shape of a classifier's output 
does not match the input shape of a loss function, they could not make a pair.

### Cross-entropy
Let's kick off with the classic cross-entropy function. If you are using Pytorch, you can refer to [the official doc
on cross-entropy function in torch](https://pytorch.org/docs/stable/generated/torch.nn.functional.cross_entropy.html) 
for the details about its actual usage. _Do keep in mind that in torch the `nn.functional.cross_entropy` does a `softmax`
by default within it, so you DO NOT need to apply `softmax` after your classifier if you wanted to._

The theory part (to be added)


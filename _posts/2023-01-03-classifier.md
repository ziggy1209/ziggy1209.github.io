# Classifier and Loss Function

As the name suggests, what a classifier does is classifying data into different categories. In a deep neural network,
a classifier usually refers to the last/output layer of the whole network. You can choose the classifier according to 
your desired output - indices or probabilities.

A loss function quantifies the differnce between the desired output and the actual output of a neural network. When the
network is handling some classification task, the choice of loss function and how the loss function is applied is usually correlated with the classifier used.

In this post, we will review some popular loss functions and classifiers frequently used in classification task.

## Classifiers

By 'classifier' we mean the functions used for classification purpose in a neural network, usually as the very last layer(s). If an activation function is used as the last layer of a neural network, it could be called a classifier. There's no specific regulation on the choice of classifier - you can use a sequence of network modules, a convolution block, a simple linearizer, or an activation function, as far as its output has the desired shape/information.

### Softmax

> The name “softmax” is misleading; the function is not a smooth maximum (a smooth approximation to the maximum function), but is rather a smooth approximation to the _arg max_ function: the function whose value is which index has the maximum. In fact, the term “softmax” is also used for the closely related _LogSumExp_ function, which is a smooth maximum. For this reason, some prefer the more accurate term “softargmax”, but the term “softmax” is conventional in machine learning.

Please mind the difference between a _softmax_ function and a _softmax activation function_. In this context, we are talking about _softmax activation function_, which is not theoretically a _soft max_. You could refer to the definition of the practical _softmax activation function_ via [the official pytorch doc](https://pytorch.org/docs/stable/generated/torch.nn.Softmax.html) and [the official keras doc](https://keras.io/api/layers/activation_layers/softmax/).

### Linearizer

As the name suggests, a linearizer is simply a linear module which maps the data to lower/higher dimension in a linear fashion.

### Regressor

A linear regressor usually consists of linear module and non-linear activation funtion. A single linear module could also be viewed as a regressor.

## Loss functions

The choice of loss function is densely related to that of the classifier - if the shape of a classifier's output 
does not match the input shape of a loss function, they could not make a pair.

### Cross-entropy
Let's kick off with the classic cross-entropy function. If you are using Pytorch, you can refer to [the official doc
on cross-entropy function in torch](https://pytorch.org/docs/stable/generated/torch.nn.functional.cross_entropy.html) 
for the details about its actual usage. In Pytorch, there is a cross entropy loss function specifically targeted towards binary classification tasks, and you can pick between `BCELoss` and `BCEWithLogitsLoss`, where a sigmoid function plus the first one is mathematically equivalent to the last one, but numerically less stable. _Do keep in mind that in torch the `nn.functional.cross_entropy` does a `softmax`
by default within it, so you DO NOT need to apply `softmax` after your classifier if you wanted to._ 

The theory part (to be added)

### Mean squared error

Kinda old-fashioned, huh? This metric can be applied if your output is a single digit and so is its target(label). You can employ mean squared error directly from the `torchmetrics` library by `from torchmetrics.functional import mean_squared_error`, and refer to [its official doc](https://torchmetrics.readthedocs.io/en/stable/regression/mean_squared_error.html) for its mathematical formula.

### Max-pooling

This one could be used in keyword spotting tasks for selecting the frame with the highest posterior probabilty - if the highest probability exceeds a certain threshold, we can view the keyword as being triggered.





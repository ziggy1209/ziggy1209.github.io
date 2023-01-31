# How The Distribution of Data Affects The Performance of A NN

As the NN learns from the data fed into it, the distribution of training data does matter. When you are given a total dataset,
you should split it by random sampling to make sure that the splitted training, dev and test sets follow the same distribution.

When working on a classification task, some may wonder should the classes uniformly distributed or distributed as they are (what's in reality/total dataset)?
 This is up to your preference on the performance of network - do you want it to be precise on atypical data or typical data?

> If the total dataset is not uniformly distributed, by having uniformly distributed training data you may be inadvertently over-weighting the importance of 
the less frequently occurring data and correspondingly under-weighting the most commonly occurring, since the loss acts as a proxy called the 
"empirical distribution" for the true underlying distribution of the data.

That is to say, high precision obtained using ML may mask strong bias. If you want the classifier to be mediocrely good
at classifying all the classes, you can have a uniformly distributed dataset; if you'd like it to be more precisely classifying
the most common data, just leave the original distribution untouched.

 
 
 

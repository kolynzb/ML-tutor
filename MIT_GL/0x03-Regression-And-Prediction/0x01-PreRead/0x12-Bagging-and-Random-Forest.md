#### **Bagging**

Before moving on to bagging, let’s define some key terms:

**Ensemble methods:** Ensemble methods mean having multiple models trained on different subsets of the dataset and aggregating their output to get the final result.

These multiple models are also called the **base models/weak models.**

There are 2 types of Ensemble methods:

1. _Bagging_
2. _Boosting_ 

In this module, we will study bagging.

Bagging is essentially **Bootstrap + Aggregation.**

Bootstrapping is a method, which is used to estimate statistics on a population by sampling a dataset with replacement i.e it resamples a single dataset to create many simulated samples. This process allows us to calculate standard errors, construct confidence intervals, and perform hypothesis testing for numerous types of sample statistics.

Aggregation is combining the results of all the algorithms to get the final result.

A Bagging classifier is an ensemble method that fits base models each on random subsets of the original dataset. These subsets are made using bootstrapping and the classifier then aggregates their individual predictions (either by voting for classification or by averaging for regression) to form a final prediction. 

![bagging-img-1.png](https://olympus.mygreatlearning.com/courses/74509/files/6958179/preview?verifier=B5lWxFwCNAh7hALTHeu474FtkwlVMhjgTFWyJjIw)

#### **Random Forest**

Random Forest is a type of bagging algorithm where the base models are decision trees, and the algorithm uses only a subset of randomly picked independent variables (features) for each node’s branching possibilities unlike in bagging where all features are considered for splitting a node.

Bootstrapped samples are taken from the original training data and on each bootstrapped training dataset, a decision tree is built by considering only a subset of features at each split. The results from all the decision trees are combined together and the final prediction is made using voting or averaging.

For Regression, we take the average of all the predictions obtained from the different decision trees as our final prediction.

![Average-rf-2.png](https://olympus.mygreatlearning.com/courses/74509/files/6958178/preview?verifier=UzJ2S64qPUJRE07As1rVKzaowfeAcoWcNhZd1ctv)

For Classification, we take the majority voting of all the predictions obtained from the decision trees as our final prediction.

![voting-rf-2.png](https://olympus.mygreatlearning.com/courses/74509/files/6958177/preview?verifier=tKquFfXedwj3n4mtyhcRfCBu59TKUbdqz0SfX2Oa)

[Previous](https://olympus.mygreatlearning.com/courses/74509/pages/decision-trees?module_item_id=3432521)

[Next](https://olympus.mygreatlearning.com/courses/74509/pages/1-dot-1-1-introduction-to-supervised-learning?module_item_id=3432525)
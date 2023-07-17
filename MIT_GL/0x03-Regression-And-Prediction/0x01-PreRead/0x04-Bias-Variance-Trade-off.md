## Bias-Variance Trade-off

Let us begin with some key terminologies that will be useful during this lecture: 

**Training data**: Training data is part of the data used to **train** the model. Generally, it is taken as a bigger fraction of the data.  

**Validation data**: This is the **smaller fraction** (in comparison to the training data) of the data used to **validate** the model. The performance of the model is iteratively validated on the validation data and accordingly. This process is called **validating** the performance of the model.  

**Testing/unseen data**: The model is finally tested on the testing data which has not been observed by the model, hence called unseen data, to get an understanding of whether the model can replicate the performance from the training data to the new data.  

**Model Complexity**: A model is considered more complex if it has a higher number of parameters that we need to estimate while training the model. The parameters refer to the coefficients associated with the variables in the model. 

**Overfitting** refers to the scenario where a machine learning model can’t generalize on the test/unseen dataset. A clear sign of overfitting is that the error on the training set is very small than the error on the test dataset, i.e., the model has fitted very closely to the training data including the noise, and hence cannot give good performance on the testing data.    

**Underfitting** refers to a model that can neither model the training dataset nor generalizes to the new dataset. An underfit machine learning model is not a suitable model and will be obvious as it will have poor performance on the training dataset.

![2sl.PNG](https://olympus.mygreatlearning.com/courses/74509/files/4905741/preview?verifier=rH5RCCCXYmztoisAF4RFaHCWRNpFV6MmYvwcnhlp)

**Bias**

In very simple terms, Bias is the amount that a model’s prediction differs from the target value, compared to the training data, i.e., the **training error**. Every algorithm starts with some level of bias because bias results from assumptions in the model that make the target function easier to learn. A high level of bias can lead to underfitting, which occurs when the algorithm is unable to capture relevant relations between features and target outputs. A high bias model typically includes more assumptions about the target function or end result. A low bias model incorporates fewer assumptions about the target function. 

**Variance**

Variance indicates how much the performance of the model would differ if different training data is used. A model with high variance would fit the training data too closely and will result in significant changes for the small changes in the dataset, i.e., the model will not give generalized performance will lead to overfitting.  

A model can not overfit and underfit at the same time, either it will perform well on the training data, or on validation data, or it will perform moderate on both the training and validation data. This creates the possibility of exchange or tradeoff between bias and variance. 

**Bias-Variance Trade-off**

If we increase the bias of an **overfit model**, we are making the model simpler and capable of generalizing over the validation set. Its performance on the validation set will **improve** and, consequently, the variance will decrease. On the other hand, if we **decrease the bias** of an overfit model, we are making the model more complex and it will not perform well on the validation set. This will cause an **increase in the validation error**. This phenomenon is called the **Bias-Variance trade-off**. 

The below image shows this trade-off between bias and variance. It shows that the model with high bias and low variance will underfit the model and the model with low bias and high variance will overfit the data.

![3sl.PNG](https://olympus.mygreatlearning.com/courses/74509/files/4905742/preview?verifier=DFWT9EDxiaOw2u5mShPrHhaiP41F7k4T0IZN6c3g)

[Previous](https://olympus.mygreatlearning.com/courses/74509/pages/best-fit-regression-line?module_item_id=3432513)

[Next](https://olympus.mygreatlearning.com/courses/74509/pages/linear-vs-non-linear-regression?module_item_id=3432515)
#### **Cross-Validation**

Cross-Validation, as the name suggests, we are cross-validating something before the final approval. Here, we are cross-validating our model by dividing the **training dataset** into 2 parts - the train and the validation datasets and then checking the performance of the model which we trained on the training dataset using the validation dataset.

There are many ways of doing cross-validation, one of the most used ways is K-fold cross-validation.

#### **K-fold Cross-Validation:**

Let’s say that there is a dataset with 1000 observations. We randomly divide them into 5 groups of equal size, called folds, and each fold consists of 200 observations.

The first fold can be kept separate to be used as the validation set, and the rest of the folds are used to train the model. After training our model, we can calculate the performance of the model on the validation set. We repeat this process K times and at each iteration, we choose a new fold for the validation set and the test of the folds for the training set.

The below image shows the process of K-fold cross-validation discussed above.

![12sl.PNG](https://olympus.mygreatlearning.com/courses/74509/files/4905735/preview?verifier=uhbyRVvTiEDeM9l4rtpDgxIXwmacRi1kJIF9xfW3)

**1. What is Supervised Learning?**

Tags: #Supervised Learning #Regression #Classification

Supervised Learning is when you already know the label of the target variable. It is of two types: **Regression** and **Classification**. Regression is when the target variable has **continuous** values and classification is when the target variable is in the form of categories or **discrete values**. For example,

1. **Regression:** House price prediction based on area, number of rooms, lawn, pool, etc.
2. **Classification:** Predicting whether a person will be diabetic in the future or not based on blood pressure, glucose, insulin, etc.

#### **2. What is Cross-Validation?**

Tags: #Cross Validation

Cross-Validation is a very useful technique for assessing the performance of machine learning models, where rather than a simple Train-Test split, the dataset is divided into many parts, and each part is used once as an auxiliary test set. The performance of the model on each part is averaged to get a final idea of prediction quality, before using the actual test set. Cross-Validation helps in understanding how the Machine Learning model would generalize to an independent data set. You want to use this technique to estimate how accurate the predictions your model makes will be in practice.

#### **3. How does K-Fold Cross-Validation work?**

Tags: #Cross Validation #K-Fold Cross Validation

Here's the thing:

- If K-fold Cross-Validation is used to optimize the model parameters, the **training set** is split into K parts.
- Training happens K times, each time leaving out a different part of the training set.
- Typically, the error of these K models is averaged.
- This is done for each of the model parameters to be tested, and the model with the lowest cross-validated and validation error is chosen.
- The test set has not been used so far.
- Only at the very end, the test set is used to test the performance of the (optimized) model.

The best combination of hyperparameters is chosen simply based on the performance - which combination of the parameters gives the best performance. Let's see how this performance is obtained:

We know that in Cross-Validation, the data will be divided into folds and each fold will be used for training and testing. Suppose, in our case, K = 5.

Therefore, the data will be split so that each iteration uses 4 folds for training and 1 fold for testing for each combination of the hyperparameters.

For example, for the first combination:

![CV 1.jpg](https://olympus.mygreatlearning.com/courses/74509/files/6958120/preview?verifier=jR2emKpAiLjbsyZG3AcfymF4wRmuJIeBPm34H2bD)

Similarly for the second combination:

![CV 2.jpg](https://olympus.mygreatlearning.com/courses/74509/files/6958121/preview?verifier=nS9dKy00a1z5EvdtkQvldSI0Ky3nXiv1QoAkEALT)

and so on.

In this way, the average performance of all possible hyperparameter combinations is assessed, and the combination that results in the best performance is chosen.

#### **4. Why do we use axis=1 for calculating row mean? Shouldn't we use axis=0?**

Tags: #axis #rows #columns

axis=0 means moving along the rows and axis=1 means moving along the columns.

So when we want to find the column means, we use **axis=0 to 'move along the rows'** to get the mean of the columns.

When we want to find row means, we use **axis=1 to 'move along the columns'** to get the mean of the rows.

#### **5. Is scaling mandatory for linear regression?**

Tags: #Scaling #Linear Regression

Scaling is not mandatory for linear regression but can be done to ensure that the units of the regression coefficients are the same.

#### **6. What is the difference between fit, fit_transform, and transform?**

Tags: #fit #fit_transform #transform

In the same way we use fit and predict in regression, similarly for functions that transform the data - we have fit and transform:

**fit:** used to fit the parameters of the function

**transform:** transforms the data using the parameters of the fit function

**fit_transform:** first fits the parameters of the function and then transforms the data as well

#### **7. How to tune a model using train, test and validation split?**

Tags: #train #test #validation #split

- Pick a combination of hyperparameters
- Train a model using those hyperparameters
- Find the model's performance on the validation test
- Repeat this process for all combinations available
- Choose the model with the best validation score, and obtain the final (generalized) score on the test set

#### **8. Why should we use drop_first=True to drop one column while creating dummies using pandas get_dummies()?**

Tags: #drop #drop_first #dummies #get_dummies

Consider a feature 'Gender' which has two categories 'Male' and 'Female'. The two new columns 'Gender*Female' and 'Gender_Male' will be formed using _get_dummies()* and the 'Gender' column will be dropped. On using *drop_first = True*, the dummy column which occurs first alphabetically will be dropped. For our example, the 'Gender_Female' will be dropped.

Dropping a column is logical because if the gender is not male, it will be female. The extra column (Gender_Female) adds no value. Even if Gender had three categories ('Female', 'Male', and 'Other' say), then also dropping one makes sense, because if it's not 'Male' or 'Other', then it has to be 'Female'.

A machine only understands numbers and the feature names make no sense to it. Whenever a nominal category column is converted to a dummy variable, the dummy variable will have values 1 or 0, i.e whether that particular row belongs to that particular feature or not. In the example that we have considered, if we check the dummy variable 'Gender_Female' for a data point and the value is 1, then the machine only understands that the value for this particular row is 1. If we include the values of the 'Gender_Male' dummy variable as well, the value there will be zero, so adding that column is not significant.

#### **9. Why do we use .fit() and .predict() ? What does .fit() and .predict() do?**

Tags: #.fit() #.predict() #fit #predict

_._**fit()\*\***:\*\* Forms a mathematical equation with the help of a training dataset

**.predict()\*\***:\*\* Uses the mathematical expression obtained from *fit()* and gives an output based on it

Consider the linear regression equation *y = a1x1 + a2x2 + a3x3*, where *x1*, *x2,* and *x3* are three different features. When we use ._fit()_, the values of the coefficients *a1*, *a2,* and *a3* are calculated, and when we use *.predict()*, the feature values for every particular row is used to calculate *y* for that row. So *.predict()* gives the *y* value as output for each row.

#### **10. Why do we split the data into test and train data while building a Supervised Learning model?**

Tags: #train #Supervised #split #training set #test set

The goal of machine learning is to make good predictions on new data drawn from a (hidden) true probability distribution. Unfortunately, the model we are building at present can't see the whole truth; the model can only sample from an available dataset. If a model fits the current examples well, how can we trust the model to make good predictions on data it hasn't seen before?

One way to understand how well the model can make predictions on unseen data is to divide the data into two subsets:

1. Training set: a subset to train the model
2. Test set: a subset to test the model

Separating the data enables you to evaluate a model's generalization capabilities and have an idea of how it would perform on unseen data. Good performance on the test set is a useful indicator of good performance on new data in general, assuming that:

1. The samples are drawn independently and at random from the distribution to create the test set
2. The test set is large enough.

Happy Learning!

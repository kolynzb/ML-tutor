## Supervised Learning - Linear Regression

Now that we have understood the basic terminologies needed, we are ready to learn about the key concepts behind supervised learning algorithms such as regression & classification.

Let’s start with an example: Suppose you're given a dataset that contains the **size** (in terms of area) of different houses and their market price. Your goal is to come up with an algorithm that will take the **size of the house as its input** and **return its market price as the output**.

In this example, the input variable i.e the size of the house, is called the independent variable (**X**), the output variable i.e house price is called the dependent variable (**Y**), and this algorithm is an example of **supervised learning.**

In **supervised learning,** algorithms are trained using **"labeled"** data (in this example, the dependent variable - house price, is considered a label for each house), and trained on that basis, the algorithm can predict an output for instances where this label (house price) is not known. "Labeled data" in this context simply means that the data is already tagged with the correct output. So in the above example, we already know the correct market price for each house, and that data is used to teach the algorithm so that it can correctly predict the house price for any future house for which the price may not be known.

The reason this paradigm of machine learning is known as supervised learning, is because it is similar to the process of supervision that a teacher would conduct on the test results of a student on an examination, for example. The answers the student gives (predictions) are evaluated against the correct answers (the labels) that the teacher knows for those questions, and the difference (error) is what the student would need to minimize to score perfectly on the exam. This is exactly how machine learning algorithms of this category learn, and that is why the class of techniques is known as supervised learning.

There are mainly 2 types of supervised learning algorithms:

1. **Regression,** where your output variable is a **continuous** variable, for example, the price of a house.
2. **Classification,** where your output variable is **categorical**, for example, approve the loan or not i.e. yes or no categories.

In this lecture, we will be learning about regression algorithms, which obviously find great use in the machine learning prediction of several numerical variables we would be interested in estimating, such as price, income, age, etc.

### Linear Regression

Linear Regression is useful for finding the **linear relationship** between the **independent and dependent** variables of a dataset. In the previous example, the independent variable was the size of the house and the dependent variable its market price.

This relationship is given by the linear equation: ![LaTeX: Y:=:\theta^{\ast}_0+\theta^{\ast}_1X:+W:](https://olympus.mygreatlearning.com/equation_images/Y%255C%253A%253D%255C%253A%255Ctheta%255E%257B%255Cast%257D_0%2B%255Ctheta%255E%257B%255Cast%257D_1X%255C%253A%2BW%255C%253A "Y:=:\\theta^{\ast}_0+\theta^{\ast}_1X:+W:")

Where ![LaTeX: \theta_0^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_0%255E%257B%255Cast%257D "\\theta_0^{\ast}")  is the **constant** term in the equation, ![LaTeX: \theta_1^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_1%255E%257B%255Cast%257D "\\theta_1^{\ast}")  is the **coefficient** of the variable ![LaTeX: X](https://olympus.mygreatlearning.com/equation_images/X "X") , ![LaTeX: W](https://olympus.mygreatlearning.com/equation_images/W "W") is the difference between the actual value ![LaTeX: Y](https://olympus.mygreatlearning.com/equation_images/Y "Y")  and the predicted value (![LaTeX: \theta_0^{\ast}+\theta_1^{\ast}X](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_0%255E%257B%255Cast%257D%2B%255Ctheta_1%255E%257B%255Cast%257DX "\\theta_0^{\ast}+\theta_1^{\ast}X")).

![LaTeX: \theta_0^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_0%255E%257B%255Cast%257D "\\theta_0^{\ast}") and ![LaTeX: \theta_1^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_1%255E%257B%255Cast%257D "\\theta_1^{\ast}")  are called the parameters of the linear equation, while ![LaTeX: X](https://olympus.mygreatlearning.com/equation_images/X "X")  and ![LaTeX: Y](https://olympus.mygreatlearning.com/equation_images/Y "Y")  are the independent and dependent variables respectively.

### What is an error?

With given ![LaTeX: X](https://olympus.mygreatlearning.com/equation_images/X "X")  and ![LaTeX: Y](https://olympus.mygreatlearning.com/equation_images/Y "Y")  in the training data, the aim is to estimate ![LaTeX: \theta_0^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_0%255E%257B%255Cast%257D "\\theta_0^{\ast}")  and ![LaTeX: \theta_1^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_1%255E%257B%255Cast%257D "\\theta_1^{\ast}")  in such a way that the given equation **fits** the training data **the best**. The **difference** between the **actual value and the predicted value** is called the **error or residual**. Mathematically, it can be given as follows:

![LaTeX: W:=:Y:-\left(\theta_0^{\ast}+\theta_1^{\ast}X\right)](https://olympus.mygreatlearning.com/equation_images/W%255C%253A%253D%255C%253AY%255C%253A-%255Cleft%2528%255Ctheta_0%255E%257B%255Cast%257D%2B%255Ctheta_1%255E%257B%255Cast%257DX%255Cright%2529 "W:=:Y:-\\left(\theta_0^{\ast}+\theta_1^{\ast}X\right)")

In order to estimate the best fit line, we need to estimate the values of ![LaTeX: \theta_0^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_0%255E%257B%255Cast%257D "\\theta_0^{\ast}")  and ![LaTeX: \theta_1^{\ast}](https://olympus.mygreatlearning.com/equation_images/%255Ctheta_1%255E%257B%255Cast%257D "\\theta_1^{\ast}")   which requires minimizing the **mean squared error**. To calculate the mean squared error, we add the square of each error term and divide the sum with the total number of records:

![LaTeX: Mean:Squared:Error:=:\frac{1}{n}\sum^n_{i=1}\left(Y-\theta_0^{\ast}-\theta_1^{\ast}X\right)^2](https://olympus.mygreatlearning.com/equation_images/Mean%255C%253ASquared%255C%253AError%255C%253A%253D%255C%253A%255Cfrac%257B1%257D%257Bn%257D%255Csum%255En_%257Bi%253D1%257D%255Cleft%2528Y-%255Ctheta_0%255E%257B%255Cast%257D-%255Ctheta_1%255E%257B%255Cast%257DX%255Cright%2529%255E2 "Mean:Squared:Error:=:\\frac{1}{n}\sum^n_{i=1}\left(Y-\theta_0^{\ast}-\theta_1^{\ast}X\right)^2")

The equation of that best fit line can be given as follows:

![LaTeX: Y':=:\theta'_0:+:\theta'_1X](https://olympus.mygreatlearning.com/equation_images/Y%2527%255C%253A%253D%255C%253A%255Ctheta%2527_0%255C%253A%2B%255C%253A%255Ctheta%2527_1X "Y':=:\\theta'_0:+:\theta'_1X")

Where ![LaTeX: Y'](https://olympus.mygreatlearning.com/equation_images/Y%2527 "Y'")  is the predicted value, ![LaTeX: \theta'_0:and:\theta'_1](https://olympus.mygreatlearning.com/equation_images/%255Ctheta%2527_0%255C%253Aand%255C%253A%255Ctheta%2527_1 "\\theta'_0:and:\theta'_1")  are the estimated parameters.

This equation is called the **linear regression model**. The above explanation is demonstrated in the below picture:

![lr.png](https://olympus.mygreatlearning.com/courses/74509/files/6958176/preview?verifier=MTseZWNVjGypcpruwNBAWKRmcd6lHQMTC5vWDsXM)

Before applying the model over unseen data, it is important to check its performance to make it reliable. There are a few metrics to measure the performance of a regression model.

1. **R-squared:** R-squared is a useful performance metric to understand **how well** the regression model has **fitted over the training data**. For example, an R-squared of 80% reveals that 80% of the **training data** fit the regression model. **A higher R-squared** value generally indicates a **better fit for the model**.
2. **Adjusted R-squared**: The adjusted R-squared is a modified version of R-squared that takes into account the **number of independent variables present in the model**. When a new variable is added, adjusted R-squared increases if that variable adds value to the model, and decreases if it does not. Hence, adjusted R-squared is a better choice of metric than R-squared to evaluate the quality of a regression model with multiple independent variables, because adjusted R-squared only remains high when all those independent variables are required to predict the value of the dependent variable well; it decreases if there are any independent variables which don't have a significant effect on the predicted variable.
3. **RMSE**: RMSE stands for **Root Mean Squared Error**. It is calculated as the square root of the mean of the squared differences between actual outputs and predictions. The lower the RMSE the better the performance of the model. Mathematically it can be given as follows:              ![LaTeX: Root:Mean:Squared:Error:=:\sqrt{\frac{1}{n}\sum^n_{i=1}\left(Y_i-\theta^{\ast}_0-\theta^{\ast}_iX\right)^2}](https://olympus.mygreatlearning.com/equation_images/Root%255C%253AMean%255C%253ASquared%255C%253AError%255C%253A%253D%255C%253A%255Csqrt%257B%255Cfrac%257B1%257D%257Bn%257D%255Csum%255En_%257Bi%253D1%257D%255Cleft%2528Y_i-%255Ctheta%255E%257B%255Cast%257D_0-%255Ctheta%255E%257B%255Cast%257D_iX%255Cright%2529%255E2%257D "Root:Mean:Squared:Error:=:\\sqrt{\frac{1}{n}\sum^n_{i=1}\left(Y_i-\theta^{\ast}_0-\theta^{\ast}_iX\right)^2}")

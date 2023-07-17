## Maximum Likelihood and Empirical Risk Estimation

To establish the relationship between variables, it is required to calculate the parameters of the model. Now that we have understood the basics of supervised learning algorithms and linear regression, let us look at how to estimate the parameters of the linear regression model. We will see the intuition of two methods that are used to estimate these parameters:  

1. Maximum Likelihood
2. Empirical Risk Minimization

###  **Maximum Likelihood** 

Let ( ![LaTeX: X_i](https://olympus.mygreatlearning.com/equation_images/X_i "X_i") , ![LaTeX: Y_i](https://olympus.mygreatlearning.com/equation_images/Y_i "Y_i") ) be a sample in a certain dataset with ![LaTeX: n](https://olympus.mygreatlearning.com/equation_images/n "n")  records. Consider ![LaTeX: Y_i|X_i](https://olympus.mygreatlearning.com/equation_images/Y_i%257CX_i "Y_i|X_i")  is an **event** that shows the occurrence of ![LaTeX: Y_i](https://olympus.mygreatlearning.com/equation_images/Y_i "Y_i")  provided ![LaTeX: X_i](https://olympus.mygreatlearning.com/equation_images/X_i "X_i")  has already occurred, i.e., given the input features ![LaTeX: X_i](https://olympus.mygreatlearning.com/equation_images/X_i "X_i") , the occurrence of ![LaTeX: Y_i](https://olympus.mygreatlearning.com/equation_images/Y_i "Y_i") . 

In the entire sample, there are ![LaTeX: n](https://olympus.mygreatlearning.com/equation_images/n "n") such events. The **likelihood** of the event ![LaTeX: Y_i|X_i](https://olympus.mygreatlearning.com/equation_images/Y_i%257CX_i "Y_i|X_i")  is the probability of occurrence of this event.

In the context of linear regression, let us consider the relationship between ![LaTeX: Y_i](https://olympus.mygreatlearning.com/equation_images/Y_i "Y_i")  and ![LaTeX: X_i](https://olympus.mygreatlearning.com/equation_images/X_i "X_i") which is as follows:

 ![LaTeX: Y_i\:=\:\theta^{\ast}_0+\theta^{\ast}_1X_i\:+W_i\:](https://olympus.mygreatlearning.com/equation_images/Y_i%255C%253A%253D%255C%253A%255Ctheta%255E%257B%255Cast%257D_0%2B%255Ctheta%255E%257B%255Cast%257D_1X_i%255C%253A%2BW_i%255C%253A "Y_i\:=\:\theta^{\ast}_0+\theta^{\ast}_1X_i\:+W_i\:")

Where ![LaTeX: \theta^{\ast}_0](https://olympus.mygreatlearning.com/equation_images/%255Ctheta%255E%257B%255Cast%257D_0 "\theta^{\ast}_0")  is the constant term in the equation, ![LaTeX: \theta^{\ast}_1](https://olympus.mygreatlearning.com/equation_images/%255Ctheta%255E%257B%255Cast%257D_1 "\theta^{\ast}_1")  is the coefficient to the variable ![LaTeX: X_i](https://olympus.mygreatlearning.com/equation_images/X_i "X_i") , and ![LaTeX: W_i](https://olympus.mygreatlearning.com/equation_images/W_i "W_i")  is the error term. 

It is assumed that the events in the **sample are** **independent** **of each other** and the error terms **follow a** **normal distribution,** with a mean equal to the prediction and standard deviation ![LaTeX: \sigma](https://olympus.mygreatlearning.com/equation_images/%255Csigma "\sigma") . Keeping in mind the normal distribution, mathematically, the likelihood function is defined as follows:

![LaTeX: P\left(Y_i|X_i\right)\:=\:\frac{1}{\sqrt{2\pi\sigma^2}}\:e^{\left\{-\frac{\left(Y_i\:-\:\theta_0^{\ast}-\theta^{\ast}_1X_i\right)^2}{2\sigma^2}\right\}}](https://olympus.mygreatlearning.com/equation_images/P%255Cleft%2528Y_i%257CX_i%255Cright%2529%255C%253A%253D%255C%253A%255Cfrac%257B1%257D%257B%255Csqrt%257B2%255Cpi%255Csigma%255E2%257D%257D%255C%253Ae%255E%257B%255Cleft%255C%257B-%255Cfrac%257B%255Cleft%2528Y_i%255C%253A-%255C%253A%255Ctheta_0%255E%257B%255Cast%257D-%255Ctheta%255E%257B%255Cast%257D_1X_i%255Cright%2529%255E2%257D%257B2%255Csigma%255E2%257D%255Cright%255C%257D%257D "P\left(Y_i|X_i\right)\:=\:\frac{1}{\sqrt{2\pi\sigma^2}}\:e^{\left\{-\frac{\left(Y_i\:-\:\theta_0^{\ast}-\theta^{\ast}_1X_i\right)^2}{2\sigma^2}\right\}}")

The above equation shows the likelihood of a single event. To estimate the collective likelihood of the entire sample of events, we need to combine the likelihood of all the individual events in the sample. 

Now, as we assumed that the events in the sample are independent of each other, we can apply the **multiplication rule of probability**. Hence, the likelihood of the entire sample of events can be given as follows: 

![LaTeX: L\left(\theta_0^{\ast},\theta_i^{\ast}\right)\:=\:\prod^n_{i=1}P\left(Y_i|X_i\right)\:=\:\prod^n_{i=1}\frac{1}{\sqrt{2\pi\sigma^2}}e^{\left\{-\frac{\left(Y_i\:-\:\theta_0^{\ast}-\theta_i^{\ast}X_i\right)^2}{2\sigma^2}\right\}}](https://olympus.mygreatlearning.com/equation_images/L%255Cleft%2528%255Ctheta_0%255E%257B%255Cast%257D%252C%255Ctheta_i%255E%257B%255Cast%257D%255Cright%2529%255C%253A%253D%255C%253A%255Cprod%255En_%257Bi%253D1%257DP%255Cleft%2528Y_i%257CX_i%255Cright%2529%255C%253A%253D%255C%253A%255Cprod%255En_%257Bi%253D1%257D%255Cfrac%257B1%257D%257B%255Csqrt%257B2%255Cpi%255Csigma%255E2%257D%257De%255E%257B%255Cleft%255C%257B-%255Cfrac%257B%255Cleft%2528Y_i%255C%253A-%255C%253A%255Ctheta_0%255E%257B%255Cast%257D-%255Ctheta_i%255E%257B%255Cast%257DX_i%255Cright%2529%255E2%257D%257B2%255Csigma%255E2%257D%255Cright%255C%257D%257D "L\left(\theta_0^{\ast},\theta_i^{\ast}\right)\:=\:\prod^n_{i=1}P\left(Y_i|X_i\right)\:=\:\prod^n_{i=1}\frac{1}{\sqrt{2\pi\sigma^2}}e^{\left\{-\frac{\left(Y_i\:-\:\theta_0^{\ast}-\theta_i^{\ast}X_i\right)^2}{2\sigma^2}\right\}}")

The above equation shows the combined probability of all the events to occur in the sample. To estimate the parameters, the above expression has to be maximized and the **maximum value** of the above expression is called the **maximum likelihood**. 

### **Empirical Risk Minimization** 

If the error is high, then it can be considered that the algorithm is not making predictions close to the actual value, i.e., the prediction is at higher risk. Hence, the **higher the error**, the **higher the risk** and vice versa.

**Empirical risk** can be defined as the **collective error** made by the model over all the training records. During the estimation of the parameters of the model, we use the **principle of empirical risk minimization** where the empirical risk is minimized to get the model parameters. The expression of empirical risk can be given as follows:  
  
 ![LaTeX: Empirical\:Risk\:=\:\frac{1}{n}\sum^n_{i=1}W_i\:=\:\frac{1}{n}\sum^n_{i=1}\left(Y_i\:-\:\theta^{\ast}_0\:-\:\theta^{\ast}_iX_i\right)^2](https://olympus.mygreatlearning.com/equation_images/Empirical%255C%253ARisk%255C%253A%253D%255C%253A%255Cfrac%257B1%257D%257Bn%257D%255Csum%255En_%257Bi%253D1%257DW_i%255C%253A%253D%255C%253A%255Cfrac%257B1%257D%257Bn%257D%255Csum%255En_%257Bi%253D1%257D%255Cleft%2528Y_i%255C%253A-%255C%253A%255Ctheta%255E%257B%255Cast%257D_0%255C%253A-%255C%253A%255Ctheta%255E%257B%255Cast%257D_iX_i%255Cright%2529%255E2 "Empirical\:Risk\:=\:\frac{1}{n}\sum^n_{i=1}W_i\:=\:\frac{1}{n}\sum^n_{i=1}\left(Y_i\:-\:\theta^{\ast}_0\:-\:\theta^{\ast}_iX_i\right)^2")

  
A higher **empirical risk** is **equivalent to** a **lower likelihood** and vice versa.
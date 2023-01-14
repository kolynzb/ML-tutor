# Covariance

- **Variance**: Variance helps us understand how far our random variable is spread out from the mean, for example, the income of the people may have a high variance as some people may have high income levels.

- The formula for variance for a sample is given by:

![alt](https://olympus.mygreatlearning.com/courses/74508/files/4905869/preview?verifier=i6ehQGBRq3kor5kS5ht8GWcFlgslnOqowXDH1Cpi)

where n is the number of samples (e.g. the number of people) and x̄ is the mean of the random variable x (mean of the income).

- **Covariance**: It measures how much two random variables vary together. e.g. The income of a person and the expenses of that person in a population. More precisely, covariance refers to the measure of how two random variables in a data set will change together. A positive covariance means that the two variables at hand are positively related, and they move in the same direction. A negative covariance means that the variables are inversely related, or that they move in opposite directions.

- The formula for covariance is given by:
  ![alt](https://olympus.mygreatlearning.com/courses/74508/files/4905870/preview?verifier=6adZ3xAg8YcxqrGqacC7rEf9Q2Yf33oGJjbhp8v9)

where n is the number of samples (e.g. the number of people) and x̄ is the mean of the random variable x (represented as a vector). 

- The variance `σ^2 x` of a random variable x can be also expressed as the covariance with itself by `σ(x,x)`.

- __Covariance Matrix__: Following from the previous equations, the covariance matrix for the two dimensions is given by:
![alt](https://olympus.mygreatlearning.com/courses/74508/files/4905871/preview?verifier=cnuNnOYRrXBxu6sWWAR24kMcsSMoOaFtbrrDmbTD)
- In this matrix, the variances appear along the diagonal and covariances appear in the off-diagonal elements.

- __Note:__ You can use the function numpy.cov to get the covariance matrix in Python.
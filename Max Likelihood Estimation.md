A model can be thought of as proving a probability distribution for specific data points.

# Linear Regression as MSE
![[Pasted image 20250130165231.png]]

Instead of producing a single prediction yˆ, we now think of the model as producing a conditional distribution p(y | x). (Goodfellow 148). 

We can imagine that with an infinitely large training set, we might see several training examples with the same input value x but different values of y. The goal of the learning algorithm is now to fit the distribution p(y | x) to al of those different y values that are al compatible with x. To derive the same linear regression algorithm we obtained before, we define p(y | x) = N (y;yˆ(x; w), σ 2). The function yˆ(x; w) gives the prediction of the mean of the Gaussian. In this example, we assume that the variance is fixed to some constant σ 2 chosen by the user.

(Page 148). 

https://medium.com/towards-data-science/probability-concepts-explained-maximum-likelihood-estimation-c7b4342fdbb1

in a binary classification problem using logistic regression, you would be trying to find the parameters (coefficients) that maximize the probability of observing the given training data (both features and labels)[1](https://learningdaily.dev/understanding-maximum-likelihood-estimation-in-machine-learning-22b915c3e05a?gi=16bca75b1b33). The objective function to maximize would be:

![[Pasted image 20250204192423.png]]

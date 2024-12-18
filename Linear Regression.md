
# General info
- The basis of all ML!
- a type of Linear Model
- AKA "Ordinary Least Squares"
- High chance of underfitting when working with less features.
- High chance of overfitting when working with more features
	- This is why alternative linear models like [Ridge Regression] are used
finds the parameters w and b that minimize the mean squared error between predictions and the true regression targets, y, on the training set. The mean squared error is the sum of the squared differences between the predictions and the true values, divided by the number of samples. 

*Linear regression has no hyperparameters, which is a benefit, but it also has no way to control model complexity.*
assumption that our target _y_ is a linear combination of the features.
For datasets with many features, linear models can be very powerful. In particular, if you have more features than training data points, any target y can be perfectly modeled (on the training set) as a linear function

# Math
For any given prediction, we used 
![[Pasted image 20240920103233.png]]

| X   | Matrix of samples x features |
| --- | ---------------------------- |
| w   | vector of weights            |
| b   | vector of biases             |


The model is fit using the **loss function** (aka objective function) called **Least Squares Minimization**

find w and b such that we minimize the sum of squared residuals (differences between observed and predicted values)
![[Pasted image 20240920102024.png]]

| y-hat | predicted target     |
| ----- | -------------------- |
| y     | actual target        |
| i     | a single sample      |
| m     | num training samples |
To minimize this function, take its derivative w.r.t. w and w.r.t. b and set that equal to 0.
This results in the following closed-form solution:
![[Pasted image 20240920103625.png]]

X is m x n matrix, where 

| m   | num samples  |
| --- | ------------ |
| n   | num features |


Often for optimization problems, we need to use an iterative approach to slowly update the weights by using the gradient to find a local minimum.
An iterative algorithm: calculate gradient, update weights, transverse gradient to find local minimum.



But if you have a closed-form solution, you can code it and solve in O(1)
BUT sometimes you still need to use the iterative approach because
1. If X is huge, doing the inverse $(X^T X)^-1$ is very computationally expensive. Its faster to do iterative
2. If we can't take the inverse $(X^T X)^-1$ 
If a problem is convex, this means that the loss function that we are trying to optimize (minimize) is mathematically convex. This means that there is a single, global minimum. Since this minimum loss it what we are trying to solve in linear regression, this means there is a global solution that the iterative algorithm is stable and will always find this solution. 
# Assumptions about data
1. Linearity: independent variables have a linear relationship with dependent vars. IF this isnt true, you can take the iteractions between features to create new features that are linearly related to the target
2. Independence: each sample is independent of the others. Not true for time-series data.
3. Homoscedasticity: the errors (in the form of residuals) are randomly distributed around the mean (0), and they have no pattern. ![[Pasted image 20241006165800.png]]
4. Normality: The errors (residual) vs X should follow a normal distribution. ![[Pasted image 20241006170125.png]]



# Problems
Problems with Linear Regression:
1. Too many predictors (features). If you have more features than samples, you can't take the inverse. 
2. Multicolinearity. One feature is a linear combination of the others. 
	1. XTX leads to an unstable solution (the weights (and predictions) change drastically from a small change in the data


Solutions
1. Drop some features (do feature selection)
2. Ridge Regression. To prevent w from changing a lot, you restrict it using the L2 norm
This becomes a ocnstrained optimization problem, but it remains a convex problem
outputs a probability, which can be converted to a label.
Once you get the output of $w^T x$ , you pass that through a logistic function to squash the output to be between 0-1.

What is the functional form for predicting the probability of a sample belonging to a positive class? Sigmoid function()

# Loss function


Why is the 0-1 loss function not used? It is not differentiable, so we cant minimize it w.r.t the weights



Log likelihood function
![[Pasted image 20240920132203.png]]

| y   | label           |
| --- | --------------- |
| p   | P(predicting 1) |
| m   | num samples     |
when label is 0, add P(pred 0) -- use right term
when label is 1, add P(pred 1) -- use left term

you are trying to maximize the log likelihood
We usually want to minimize an optimization function, so we use negative log likelihood (NLL)

*convex function, so we can find global optimum*
*it won't matter where you start, it will always converge on the optimal solution.*

 *no closed-form solution*


Simple linear model for classification
![[Pasted image 20240920130409.png]]
0-1 loss function
==*loss is either 0 or 1*== 
==*problem: it is non-differentiable*==

Other loss functions that closely mimic it and are differentiable:

# Hinge Loss:

![[Pasted image 20240920131258.png]]
the $yw^T x$ term is positive when the signs of the answer (y) and prediction ($w^T x$) match, resulting in a loss closer to 0.
When the signs don't match, the loss is closer to 1

# Logistic Loss
used for logistic regre

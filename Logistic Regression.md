outputs a probability, which can be converted to a label.
Once you get the output of $w^T x$ , you pass that through a logistic function to squash the output to be between 0-1.

What is the functional form for predicting the probability of a sample belonging to a positive class? Sigmoid function()

# Loss function

> [!spoiler] 
> It is not differentiable, so we cant minimize it w.r.t the weights


Why is the 0-1 loss function not used? 
```spoiler-block
It is not differentiable, so we cant minimize it w.r.t the weights. As long as we’re not on the classification boundary, making a small enough change to wj will have no effect on L0−1, because the prediction won’t change. This implies that ∂L0−1/∂wj = 0, as long as we’re not on the boundary. Gradient descent will go nowhere. (If we are on the boundary, the cost is discontinuous, which certainly isn’t any better!)
```

Why is the squared error loss function not used?
$y = w^Tx + b$
$LSE(y, t) = 1/2(y − t)^2$


```spoiler-block
We don't want to have to exactly predict the label every time. If our classifier is very confident a sample is pos class, y=9 and even if t=1, the error is large.
```

Even when sigmoid is added, why isn't squared error loss used?
```spoiler-block
Strangely, dLSE/dz gets smaller the more wrong you are. the more confident the wrong prediction, the smaller the gradient is! The most badly misclassified examples will have hardly any effect on the training. it has a bad "gradient signal" for those training examples.
it doesn’t distinguish bad predictions from extremely bad predictions
```


## Cross-entropy, the solution
![[Pasted image 20250126191807.png]]
equivalent to $LCE(y, t) = −tlog y − (1 − t) log 1 − y.$
Cross-entropy solves the previous problem because it draws big distinctions between probabilities close to 0 or 1


Log likelihood function
![[Pasted image 20240920132203.png]]
LL function still just gives p(y|x). Its just written using logs **to avoid multiplying a bunch of probabilities together (which can lead to numerical underflow)** 
Instead of maximizing the LL, we minimize the negative LL

# Difference b/w NLL and Cross-Entropy
- NLL is the same as the cross-entropy b/w the training data and model distribution (the model's predictions)

| y   | label           |
| --- | --------------- |
| p   | P(predicting 1) |
| m   | num samples     |
when label is 0, add P(pred 0) -- use right term
when label is 1, add P(pred 1) -- use left term

you are trying to maximize the log likelihood
We usually want to minimize an optimization function, so we use negative log likelihood (NLL)




Simple linear model for classification
![[Pasted image 20240920130409.png]]
0-1 loss function
==*loss is either 0 or 1*== 
==*problem: it is non-differentiable*==

Other loss functions that closely mimic it and are differentiable:

The sigmoid function to the rescue!
Sigmoid function is used as the activation function.
It is differentiable.
$z = w^T x + b$ = "logit"
y = $sig(z)$
because y is b/w 0 and 1, we can interpret it as estimated prob that t=1


# Hinge Loss:

![[Pasted image 20240920131258.png]]
the $yw^T x$ term is positive when the signs of the answer (y) and prediction ($w^T x$) match, resulting in a loss closer to 0.
When the signs don't match, the loss is closer to 1

# Logistic Loss
used for logistic regre

# Why use gradient descent?
Even though linear regression is convex, there is no closed-form solution
[[Convexity]]
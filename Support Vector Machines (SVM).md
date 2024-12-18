
# Margin
Distance between the hyperplane and the closest data points from each class (the support vectors) #look_into The goal of SVMs is to max this margin while min classification errors. A large margin indicates a greater degree of confidence in the predictions, since it means there is a larger gap between the hyperplane and the closest data points from each class. This margin is a measure of how well separated the classes are in feature space.


# Support Vectors
The samples that lie closest (or on) the decision boundary are the support vectors. These data points are important because they determine the poisition and oreientation of the hyperplane, and thus have a significant impoact on the classifiaction accuracy of the SVM. In fact, SVMs are named after these support vectors because they "support" or define the decision boundaries.

What are support vectors #interview_question 

# General info
goal is to find two boundaries that are parallel, linear boundaries so that no points lie between these two boundaries and they separate the classes.
Goal is to max the distance between the boundaries

==intuition behind using two boundaries instead of one is to reduce the model's variance when one point slightly changes.==

convex (quadratic) optimization boundary
- easily extendable to non-linear 

You *decide* what the width is (hyperparameter) and *learn* what the support vectors are
# Hard-margin SVMs
2 Requirements
1. There are no points within the two boundaries
2. The distance between the boundaries is maximized
there is a middle plan $yw^T x$
where there other two boundaries are $yw^T x$ +/- lambda

To max margin, min the norm of the weights

For ever optimization problem which we normally define as a minimization problem, you can define a dual that is a maximization problem. If primary is min, dual is max, and vice-versa


For SVMs, primal is minimation, which is solved "in the space of w, which is of length n (features)" (we are trying to find a w s.t. ...)

The dual is a maximization problem which is solved "in the space of alpha, which is of length m (sampels)"

For SVMs, we can solve the primal or the dual optimization problem because this problem is convex, meaning both answers will be the same

Alpha values can be thought of as weights that determine how much each support vector "pulls" or "pushes" the decision boundary.**Dual Formulation**:  
In the dual formulation of SVMs, the problem is expressed entirely in terms of these alpha values, eliminating the need to directly compute the weight vector w


![[Pasted image 20240920141103.png]]

For i samples, there are i alpha values that make the above equation true. For any points where $y(w^T x + b)$  is >1 or < -1, the only way to get that equation to 0 is alpha = 0

$y(w^T x + b)$ should be pos
1 - $y(w^T x + b)$ should be neg
only way to get the whole equation to go to 0 is when alpha is 0
alpha(1 - $y(w^T x + b))$ gives P (pred 0)

if $y(w^T x + b)$ =1, then a(0) = 0 and alpha can be nonzero. These points are support vectors
this means alpha could be nonzero

alpha will be 0 for all non support vector points
alpha can be non-zero for support vectors

![[Pasted image 20241011094041.png]]
When making prediction, iterate through all i samples. Remember, the samples were alpha has to 0 result in adding 0 -> the only samples that matter are the ones where alpha is nonzero. 
In those cases, take the dot product (distance) between the sample you are predicting x and the support vectors xi. ==You need the support vectors to make predictions!==

Ultimately in the primal (maybe the dual?) SVMs are trying to minimize hinge loss

The rest of the prediction is intuitive: you take the distance between the sample you are trying to predict and the support vectors, and multiple it by 1. yi (to decide which class) and 2. alpha ()...

Since the final model relying on some of the data points, you need to take some of the training data with you when you point the model in prod

at the end, length of alpha will be same as the amount of non-zero values of alpha, which will be the support vectors
## How to choose?
When you have more samples than features, use primal
When more features than samples, use dual

# Soft SVMs
Why use soft-margin SVMs?
One outlier in a hard-marginSVM can significant change the support vectors and lead to much worse generalization accuracy. This is why hard-margin SVMs have high variance. A soft-margin allow the tradeoff of some misclassifications to achieve a better generalization accuracy.

Soft-margins are used when the data is not linearly separable because such a dataset will always have error (if using a linear kernel)

Prediction includes a (x * xi) term. These points are the support vectors and get replace with the kernel function. 
allow for some errors
introduce error term that is >0 for points that are in between boundaries

it simplifies to hinge-loss

you end up having an upper-bound on alpha (we cant find the best alpha because we will have to decide how many points we are willing to get incorrect in exchange for a larger alpha)

The number of alpha values (model parameters) is the same size as the number of support vectors

## Introduces C for regularization
C controls the penalty for misclassifications.
Low C = more regularization = wider margin = more misclassifications = better generalization = possible underfitting

alpha is inversely proportional to C

# Kernel SVMs
- Non-linear versions pf SVMs
- Project data into higher dimensional space using a phi function on X
- The Kernel Function encapsulates this by both projecing the data to a higher dim space and finding the dot product (distance b/w two points). The output is a single num
- Whenever we need a phi(x), we actually need the dot product of them, so we can just use the Kernel Function

## Gaussian Kernel
![[Pasted image 20241011102658.png]]
Intuition is that the points can be projected into an infinite dimensional space, and youll alwyas be able to separate points in lower spaces in a higher dim space. This, you can separate the points perfectly (achieving a training error of 0). The gamme aocntrols the dim of the space? #look_into 

In general, when the problem isn't linearly separable, the support vectors are the samples within the margin boundaries. Otherwise, they lie on the boundaries.

Gamma is a coefficient that multiplies the distance between the sample we are trying to predict and a support vector. Since it is neg exp, a larger gamma means that the calculated distances matter less and less



gamma up, complexity up, variance up
==Why? A higher gamma value means that the influence of each training point is more localized==



In the high dim space,a linear hyperplane can separate the data. While the decision boundary in the higher-dimensional space is linear, it corresponds to a non-linear boundary in the original feature space, making these types of SVMs non-linear models
## Kernel Trick
Kernel function can avoid explicitly projecting the points to a higher dim space. Since we always want to find the dot product of these higher dim points we find a mathematically equaivallent function to projecting the points and then finding the dot prouct that can be done in one step.


C is the tradeoff between the error and the margin size

There is a hyperparameter for the kernel type



# C
A low C is not simply just widening the original path until the required toleralnce level is met. It means createing anew widest path by misclassifying the min poitns such that it is below the otleratnce threshold. C controls the [[Model Complexity#Bias-Variance Tradeoff]] 
A larger C emphasizes correct classification of training points, increasing variance. A smaller C allows for more margin violations, which increases bias by making the model simpler? #look_into 




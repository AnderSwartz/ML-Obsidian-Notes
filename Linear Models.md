A model is a class of hypothesis or functions used to transform inputs to predicts. 
A hypothesis is a specific instance of trained parameters

Loss function is for single instance: $L(y,t)=1/2(y-t)^2$
Cost function is the loss function averaged over all training examples:
$J(w,b) = 1/2 \sum_{i=1}^{N}(y^i -t^i )^2$
	$= 1/2 \sum_{i=1}^{N}(w^T x^i +b -t^i )^2$


The cost function is what gets optimized. 

# Linear Classification
#interview_question 
Why are classification error and squared error problematic cost functions for classification?

What is cross-entropy and why is it easier to optimize than squared error

#interview_question 
How can binary logistic regression be generalized to multiple variables

# Limitations
Using a polynomial feature mapping (transforming input x to any high-degree polynomial), you could find a linear model that can fit a solution to any regression or classification training data. 
Problems:
- overfitting
- Order of growth of the polynomials is worse than exponential
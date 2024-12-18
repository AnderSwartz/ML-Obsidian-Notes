# Ridge Regression
- Includes alpha hyperparameter which penalizes more extreme weights. 
- Higher alpha = weights closer to 0
- Called L2- norm
- Exists a closed-form solution
- C is inverse of alpha
	- This matches [[Support Vector Machines (SVM)]], which larger C is actually less regularized!
# Lasso Regression
- Same as ridge but the penalty term is calculated slightly differently
- Called L1-norm
- No closed-form solution
- Promotes feature selection by reducing some coefficients (weights) to 0
- Positive Lasso is where you impose the constraint that all weights are 0 or greater
# Elastic-Net
- Combines both L1-norm and L2-norm via "convex combination"
- No closed-form solution

# C
A C increases (radius of n-dim sphere), alpha decreases and the penalty is smaller

Interview Q: What is an L1 or L2 norm, and when do we use one vs the other?
The constrain has...

In L2, the weighs are constrained to an n-dimensional sphere.
Since the L1 norm constrains the weights to an n-dimensional diamond, the intersection of the error contours and the weight space (diamond) will always be one of the corners

Lasso doesn't have closed-form solution



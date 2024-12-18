- Another instance of [[Ensemble methods]]
- When people say gradient boosted trees, they mean this
# Gradient boosted Trees
Generally typical model for structured (tabular) data

- The residuals for the predictions form the first dataset become the y for the next dataset.
- each try tries to fit to all the errors of the previous tree. 
- You can overfit and having perfect training score
- Tons of hyperparameters
	- usually you just choose a few

Regardless of if you are solving a classification or regression problem, each tree with be a regression tree (because of the way we are modifying the y)

1. F0 classifier is base classifier (model predicts average of target). For classification with 60% samples y=1, prediction is .6
2. Take residuals from F0 and get residuals. Now, you have a continuous target instead instead of a categorical target, which is why it is framed as a regression problem for each of the individual trees going forward.
3. Later during training, the weights (for each features) are updated using the same value as the residual. Gradient = residual. Every time you built a tree you are building against the gradient, so you are  taking the optimal step in the right direction down the loss function.


What is the "gradient" in gradient boosted trees? #interview_question
Take "gradient" of a loss function w.r.t. w and then keep updating the weights.
The gradient ends up just being the residual!
This means that each new tree is "built against the gradient" of the last tree

the general idea is that the gradient gives the direction and magnitude of the updates needed to minimize the loss, and this update is driven by the residual errors in the predictions.

Functional form (for predictions):
![[Pasted image 20241011130332.png]]
gamma У is the weight of how much each tree's prediction contributes to the overall prediction

# Hyperparameters
- Num estimators (trees)
- Learning rate
- Decision tree parameters
- regularization params

# HistGradientBoosting
puts the value of each feature into bins. Then, when splitting, instead of checking every possible value in that feature, just check the width? of the bins. Hist for histograms.

# XGBoost
mature ecosystem.

# LightGBM
When building from one tree to another, define a threshold where, for points with low residuals, we sample the points. 

# CatBoost
uses target encoding for cat features



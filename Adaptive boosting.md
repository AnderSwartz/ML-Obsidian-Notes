Adaboosting

# Alpha
Each tree (stump) has an alpha that determines how much it contributes to the final prediction. The alpha is inversely proportional to the error. A model with less error should contribute more to the final prediction

# Weights
Each sample also has a weight that impacts the loss when training the trees


- Typically, all trees are *decision stumps (tree of depth 1 = 1 split)*
- The error from one classifier to the next is carried over through the weights of specific samples. Samples that were predicted incorrectly on the last classifier with have a higher weight for the next classifier
# Algorithm


- weights are initialized to all be 1 / N for all N data points
- Then for each tree in the model:
	- fit a classifier to the training data
	- sum up all the incorrect predictions multiplied by their associated weights
		- This gives a measure of error for that classifier
	- Create an alpha that is inversely proportional to error. Good alpha = good model
	- This alpha is used a weight for that classifier in making the final prediction
	- For the data points that were correctly predicted, those weights stay the same. For incorrect predictions, those weights increase using alpha
	- *The error is transferred from one error to another is the weights*
	- Even in [[Linear Regression]], the larger weights will correspond
- When it is actually training, we define a loss function that we try to miminize just like the other techniques. This exponential loss function is differentiated w.r.t. alpha and G (the tree). 


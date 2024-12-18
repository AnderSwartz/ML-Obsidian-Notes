
# Pros
- The can generate non-linear boundaries
- They are simple to implement in production because they are a bunch of if-else rules
- Easily interpretable
- The rules are comprehensive, meaning you can make a prediction for any point
- You can test the quality of the split for each feature separately, allowing you to parallelize this process well

# General info
The leaf nodes are not necessarily all one class or another (pure). Majority voting is used, or in regression the mean target value is used.
When all leaves are completely pure, training error is 0? #look_into 
You can always build a tree to complete purity where all leaves have 1 point (super overfit)
Greedy because it splits using the max info gain at that location, but doesn't look ahead.

## Gini / Entropy
Measures of impurity for classification
## MSE / MAE
Measures of impurity for regression

# Splitting
You can't just use the split that results in the lowest gini because sometimes the gini increases in a child node!

For each feature:
	For each value of that feature:
		Do a split
			Take a weighted avg of the entropy of both of the children. The weights are the proportion of the data in the children. 
			To find **info gain**, take this weighted avg of entropies and do the entropy of the parent node minus this
			
For categorical features with > 2 values, do target encoding, allowing you to order the categories. Once ordered, there are only n-1 splits for n categories, instead of 2^n -1
# Hyperparameters

## Pruning
- Built tree to complete optimality (purity) and then start removing pure nodes. 
- A bit redundant because we could just not build the tree to purity
## Early Stopping
1. Max Depth
2. Max leaf nodes
3. Min samples split 
4. Min info gain


# Feature importance
P(any sample reaches that node) * info gain at that node

- The features that are higher in the tree are more important because they provided the maximum info gain
- Num of samples that a feature is impacted. This is calculated by the number of samples that reach that node At same level, two splits might impact different numbers of points. 
- Features can appear multiple times. Sum each time
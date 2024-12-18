- An ensemble of decision trees
- Uses bagging to generate unique datasets for each tree
- Keeps tracking of all samples that bootstrapped sample does not contain. These are *out-of-bag (OOB)\*
	- This gets used for validation and results in a *OOB error* - an average of the error that each tree has on its OOB samples. This is used for hyperparameter tuning and essentially replaces cross-validation for random forests.
- Also does random sampling of cols
	- For each training dataset (1 per tree), sample only some of the cols (usually square-root of n total features)
- When predicting, the input is passed to every decision tree. ==The outputs of every tree are averaged to make final prediction==
- Each tree is independent from each other, enabling parallelism
- what is warm start? #look_into 

## Intuition
- When you sample the columns, you give other cols a change to contribute
- You give all these features a chance to contribute
- The final prediction takes in information from models that have learned to use different features

## Hyperparameters
- Same hyperparameters for [[Decision Trees]] plus,
- num trees
- num features (often sqrt(num features) for classication, num features for regressions)
- OOB error

# Feature importances
You calculate the feature importance as normal for each decision tree and then sum them

# One vs rest
- For n classes, builds n classifier
- Predictions is made by passing sample to all n classifiers and using the classifier with the top score
- Good for imbalanced datasets (why?)
	- by combining all other classes into one group, the OvR approach allows the classifier to better recognize the patterns specific to the minority class without being overwhelmed by the majority class data

# One vs One
- For n classes, needs to have binary classifiers for every combination of class n(n-1) / 2 classifiers
- Prediction is made by majority voting. Each classifier contributes a vote (not score!) for its classes. The class with the highest total votes among all classifiers wins
- Good for balanced dataset
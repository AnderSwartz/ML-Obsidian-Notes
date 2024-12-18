# Training Data
## Random Splitting
- size of data determine by a ration
## Stratified Splitting
- Ensures that the ratio of samples that belong to each class are the same between training and testing datasets
	- Say there are two classes. This splitting technique goes into each class and does the 80/20 split and then combines the training data from each class to form the overall training data, and same with the testing
- Good for highly imbalanced datasets
## Structured Splitting
- Used for time-series data
- If you want to train on the last 7 days (besides yesterday) and test on yesterday

# Testing data
- Purpose of the testing split is to evaluate the FINAL OPTIMAL MODEL (model that is trained with the best hyperparameters)
- Performance on testing data should give you an idea of how the model will perform in production

# Validation data
When doing [[Hyperparameters#Hyperparameter Tuning]] we don't want to use the testing data because of data leakage. This is why we have a validation set.

This is where [[Cross validation]] comes in
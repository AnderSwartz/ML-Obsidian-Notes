# Three-way holdout
do the normal train (often called development) and test split
The further split train into train and validation.
Used the most

# K-fold CV
After the normal train / test split, split the train into K equal "folds". Then for each hyperparameter combination, train a model on all of the folds besides 1. Then evaluate on the last fold. Since there are K folds, there are K different folds to use as the evaluation fold, meaning that each hyperparameter combination requires K models. For each hyperparameter combination, take the average of the accuracy when evaluated on all K folds.
Used when model training isn't expensive
# Repeated K-fold
where the split into different folds is repeated each time
# Leave-one-out CV
For small datasets, say 10 samples, we assign each sample to its own fold

# Stratified K-fold CV
preserves the ratios of samples in each class

> #flashcards
> 
> 
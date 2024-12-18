They control the [[Model Complexity]]. Think of the "depth of tree" hyperparameter in decision trees. This controls how complex and large the model is.

- Model parameters are LEARNED during the training process.
- Hyperparameters are TUNED during the training process.

Hyperparameter tuning is where we find the best hyperparameters that achieve the best validation score?

The number of different models that you have to try train is often decided by the number of hyperparameters you want to vary.

A lot of ML Engineering is the process of taking the optimal model and deploying it into production.


Oftentimes, pushing lambda will result in w going to 0.

# Hyperparameter Tuning
## Uninformed search strategies
Uninformed search means that up front, the programmer decides the points that will be search (in hyperparameter space) and then they train models with each combination. This also means they can be run in parallel (use package RAY)
## Grid search
search lambda over a grid. Give range and intervals. from 0-1 with intervals of .1. So I have 10 models for each value of lambda. It is a GRID because sometimes there a 2 hyperparameters to tune at the same time. 

## Random search
- empirically proven that random search is better than grid search
	- This is because in grid search, we use the same values (e.g. .1, .2, .3, etc.) for every search. But random search will explore different values per hyperparameter better
	- The potential combinations of hyperparameters grows exponentially, lead to grid search being very expensive with more hyperparameters
- Often times there are many hyperparameters, some which are more important than others

## Why is random search better?
You get to search a larger space (more variation in hyperparameters) for the same amount of tries. Especially when there are some hyperparameters that are much more important than others, it is important to find its best value, which random search will excel at.


## Informed search strategies
Informed because based on how the model performs on each hyperparameter combination, you change the next combination. The tradeoff is that this requires work to be done between each hyperparameter combination.
- Bayesian optimization

Sometimes there are combined strategies. Random search -> grid search
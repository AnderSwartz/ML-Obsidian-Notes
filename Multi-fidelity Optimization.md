"Fidelity" is referring to *budget*
*Budget* is the resources allocated for training a model, often time, number of trees (in ensemble methods), or percentage of dataset

Intuition is that we can search the hyperparameter space (often with random search) with a low budget to find promising areas. Then we slowly increase the budget as we eliminate different hyperparameter combinations within the promising areas.

# Successive Halving
Start with many hyperparameter combinations that all have a small budget. Each iteration, only take the top half of the combinations that have the best validation score to the next iteration. On the next iteration, double the budget.

# Hyperband
Intuition: The impact of some hyperparameters (such as learning rate) will heavily depend on budget. Even if a smaller learning rate it the theoretically the optimal, only testing learning rates with a small budget (small number of tree in RFs) will incentivize a larger learning rate

It is also unclear how many different combinations to initially consider and how much to reduce the combinations and increase the budget each iteration -> it runs multiple rounds with different initial budgets

# Bayesian Optimization Hyperband
At each iteration, the configurations are chosen using Kernel Density Estimation (KDEs)
instead of being random
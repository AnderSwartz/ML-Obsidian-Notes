# General Info
Model interpretation should not be confused with causal inference.
It is not about explaining the data, but it about explaining the model itself

# Global Interpretation
What are the most important features, and how do the dependent variable?

## Linear Models
Can plot correlations of each feature with the target

Relative importance of coefficients is only meaningful if the features are scaled.
### Lasso
For correlated features, L1-regularization will randomly select one of these as important and drop the others, making it hard to interpret

## Tree-based models
Feature importance is the decrease in node impurity (or increase in info gain) * P(a sample reaching that node)

Random forests can be susceptible to noise in the data, showing feature importance for random features

## Drop feature importance

Feature importance is measured as the drop in performance when the model is trained without the feature

## Permutation feature importance

After training the model, one at a time you select each feature in the dataset and randomize its values. Now evaluate the model with each of these datasets.

It is fast because you don't have to change the model, and you can parallelize


# Local Interpretation
for a specific data point, why is the model making a certain prediction

## LIME
Local Interpretable Model-agnostic Explanations

good for explaining what contributed to a specific recommendation online

Giving a specific data point, perturb it to create multiple similar points. Make sure these points are close.
Sometimes weights are applied to each data point according to how similar they are to the rest (or the original sample)

Then, make a prediction on all of these points

Now, there is a new dataset consisting of the original point and the synthetic points along with there predictions.

Then train a new linear regression model on this dataset.

## SHAP
Inspired by Game Theory
Provides both local and global explanations.

### intuition
trying to explain diff b/w prediction and avg prediction (avg of target)

Say the avg target is 310k but my regression predicts 300k. SHAP tries to explain that 10k difference.

keep one feature constant (value) and permute through all the values of other features.

For just n binary features, there are 2n combinations.

## Partial Dependence Plots (PDPs)

Get all data points where a feature has a certain value, and look at the avg prediction for those points.

# Univariate Statistics
Asks "is there a statistically significant relationship between each feature and target?". In the case of classification, this is also known as analysis of variance (ANOVA).
They are *univariate* because they only consider each feature **individually**

# Model-Based Feature Selection
Model-based feature selection uses a supervised machine learning model to judge the importance of each feature, and keeps only the most important ones. 
Decision trees and decision tree–based models provide a `feature_importances_` attribute, which directly encodes the importance of each feature. Linear models have coefficients, which can also be used to capture feature importances by considering the absolute values. 
Linear models with L1 penalty learn sparse coefficients, which only use a small subset of features. This can be viewed as a form of feature selection for the model itself, but can also be used as a preprocessing step to select features for another model

# Iterative Feature Selection
Model-based, but starting with no features and adding features one by one until some stopping criterion is reached, or starting with all features and removing features one by one until some stopping criterion is reached
**computationally expensive**

# Utilizing Expert Knowledge
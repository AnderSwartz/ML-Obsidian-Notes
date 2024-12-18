# General info
More polynomials (degrees?) is more complex.
Model Complexity is controlled by the hyperparameters.
The "Saddle Point" is the point at which making the model more complex will start to decrease the test accuracy and result in overfitting
- If a model is able to capture the underlying distribution of the data, then slight variations of the data are not going to change the model much. If the model is too sensitive of the data, then it has not captured the underlying distribution and the predictions are going to vary a lot.

# Bias-Variance Tradeoff
If a model was able to capture the underlying distribution of a data set, slight variations in the training data should not drastically change its predictions

High variance
## Underfitting = how bias, low variance
Lets say you are predicting house prices and there are 100 features but your model only uses # of bedrooms. This is a simple and *biased* model because it doesn't really matter what data you give it; the model predictions don't change a lot. Simple models are using the data less, so they are less dependent on the data.

## Overfitting = low bias, high variance
If you create new features on top of the OG 100 features and you use all of them to build a very complex model. If you change the data a little bit, there could be so much variance that the predictions would change a ton. 

A low bias means that the model has low or no assumptions about the data. Bias occurs due to wrong assumptions about the data such as assuming data is linear when its actually more complex. It also comes from not having enough samples or when the sampling between train and test is not actually independent

# Other tradeoffs
There is a tradeoff between the most optimzed model that uses more features vs the increased complexity for gathering the data with thsoe extra features, training with those features, and predicting. Sometimes the additional model performance is not worth it.


serves as a simple non-parametric model to compare more complex models with.

- Any single prediction is computationally expensive because you have to calculate the distant from that sample to every other point.
	- Efficient optimizations for this like "approximate nearest neighbors"
- There is no training!
-  The distance can be euclidian distance or anything you want
- It performs worse at higher dimensions because of the [[Curse of dimensionality]]


- no parameters besides k
- fits on training data like other models
- For a new point, predicts the majority class of the k-nearest neighbors
- Finding the distance to all neighbors can be expensive with lots of points or dimensions
- You can choose distance technique
- *The notion of distance breaks down at higher dimensions*
- *Training is trivial (you just store the training data), while prediction is expensive*
- For regression, predicts the average value of k-nearest neighbors


how does the train and test error change when you change model complexity
how do you choose your optimal hyperparameters
What is bias - variance tradeoff

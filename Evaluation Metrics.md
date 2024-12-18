# General Info
- Gives us a measure of confidence in the model
- Deciding which metric to use will decide what tradeoffs we want

# Classification Metrics
## Threshold metrics
Define a threshold where you make sure the point is classified one way or another
- accuracy
	- Correct predictions / total predictions
	- What are limitations of accuracy?
		- In an imbalanced dataset, accuracy can be misleading. 
		- A 90% accuracy could be acheived when you predict one class all the time. The only way to tell is by looking into the data
- precision, recall and F1
	- Good for telling us how models do per class
	- Macro takes average of these scores (precision, recall and F1, normally recall) for each class. E.g. for binary classification, two F1s are found. The macro is the average of these
	- Weighted is when you weight these scores by the number of samples in each class.
- Balanced accuracy: average of accuracy for each class

## Ranking

- Average precision (AP)
- Area Under Receiver Operating Curve (AUROC)

You care about improving predictions minority class
Improvements in the minority class will impact the precision more than FPR. Therefore, average precision is better than AUC 


Ranking metrics are better for not having to care about the threshold

caring about minority vs majority class, precision vs recall is problem-specific

Choose precision when cost of FP is high
Choose recall when cost of FN is high

# Regression
- R2 (coefficient of determinations): proportion of the variance in the dependent variable (the target) that is predictable from the independent variables (the features). R2 = 0 is a model that is as good as always predicting the mean
- MSE. the mean of the squared error (redsiduals)
	- Can be used as a loss function or evaluation metric.
- Mean absolute error: minimizes impact of outliers
	- Usually, the error is squared, mean that larger mistakes contribute to exponentially more error. Using absolute error avoids this
- MAPE: Error relative to input 



| TN  | FP  |
| --- | --- |
| FN  | TP  |

Normalized by rows (actual)

| TNR<br>TN/TN+FP | FPR<br>FP / FP + TN                        |
| --------------- | ------------------------------------------ |
| FNR<br>FN/FN+TP | Recall = sensitivity = TPR<br>TP/TP+FN<br> |
Normalized by cols (predictions)

|     |                       |
| --- | --------------------- |
|     | Precision<br>TP/TP+FP |

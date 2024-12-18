 ![[Pasted image 20240917205847.png]]

These values are class-specific (label chosen is 1). They can be calculated for each class. The minority class is typically the minority class (cancer)
# Precision
"Out of all the samples that I predicted 1, how many were actually 1?"
It is w.r.t to the predicted values
Precision =  TP / (TP + FP)
Precision measures how many of the samples predicted as positive are actually positive.
Used for limiting FP
AKA "positive predictive value (PPV)"

# Recall
"Out of the samples that were actually 1, how many did I predict as 1?"
w.r.t. the actual values
Recall = TP / (TP + FN)
Recall measures how many of the samples that are actually positive were predicted positive
used for minimizing FN
Other names for recall are _sensitivity_, _hit rate_, or _true positive rate_ (TPR).
ALERT, I have a tendency to think its TP / (TP + TN), but TN does not give samples that are actually P, FN does!

Assume class 0 has much more samples than class 1. 
assume in our application it is more important to have a high recall for class 1, as in the cancer screening example earlier. This means we are willing to risk more false positives (false class 1) in exchange for more true positives (which will increase the recall)
## False positive rate

FPR = FP / (FP + TN)
the fraction of false positives out of all negative samples:
# Accuracy
Accuracy = TP + FP / all

# F-1
(P * R) / (P + R)
The f1-score only captures one point on the precision-recall curve, the one given by the default threshold.
# Operating Point / Threshold
Setting a requirement on a classifier like 90% recall is often called setting the _operating point_

We can plot a precision_recall_curve using just the number of samples we have in each class.


One particular way to summarize the precision-recall curve is by computing the integral or area under the curve of the precision-recall curve, also known as the average precision

For a sigmoid that outputs 0-1, moving the threshold above .5 optimizes for precision (makes it harder to predict 1).
Threshold below .5 optimizes for recall.

Comparison between models is dependent on the threshold you choose. 

[[ROC Curves]]
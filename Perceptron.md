Standard Rosenblatt "Alpha Perceptron":
![[Pasted image 20250119113550.png]]
The red weights are the **only** things that are learned
![[Pasted image 20250119114033.png]]

This simple learning procedure is guaranteed to find the optimal set of weights if such weights exists


# Updating weights
![[Pasted image 20250119193541.png]]



how the error changes as we change the weight is how the error change when we change the prediction times how the prediction changes as we change the weights

See notebook!



![[Pasted image 20250119202143.png]]


# Full perceptron algorithm
![[Pasted image 20250125155607.png]]

If the prediction is correct, we do nothing. If it is wrong, we adjust the weights in a direction that makes it more correct.
If the training case is positive and we classify it as negative, we’d like to increase the value of z. 
Conversely, if it’s a negative example which we mistakenly classified as positive, we want to decrease z
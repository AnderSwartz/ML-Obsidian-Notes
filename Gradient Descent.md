Single Variable Example:
![[Pasted image 20250127223953.png]]


# Batch gradient descent
Takes all the examples (or in batches) and **averages** the gradients.
![[Pasted image 20250213165956.png]]
For each param, take the partial deriv of cost w.r.t that param, add that up for all training examples, and divide by N (number of examples)

# Stochastic gradient descent
Other extreme of batch. It updates after every example
Its stochastic because the single example it updates on is randomly chosen.

Motivation:
- its computationally expensive to add all the gradients up and some them for each param (and them divide)
- It can make progress before seeing all examples, allow faster learning 

Drawbacks:
- the gradient of one example can be pretty noisy
- We can't exploit efficient vector and matrix operations and parallelism (GPUs)
	- larger GPUs allows for bigger batch size

For efficiency, we can compute the gradient for each sample.
Stochastic gradient descent updates the weight vector one data point at a time.
One pass through of all the data is an epoch.

Its an unbiased estimate of batch gradient descent

#look_into 
Advantage is that it handles redundancy in the data (same training examples)

Another advantage is that it can get out of local minima better, since the gradient of the cost function at one sample is less likely to get stuck than when its computed over the whole dataset.

![[Pasted image 20250213170642.png]]

# Mini-batches
A compromise!
A downside of stochastic gradient descent is that the gradient of the error function computed from a single data point provides a very noisy estimate of the gradient of the error function computed on the full data set.  

larger mini batches have less variance, linearly

A batch size of S has the variance of a batch size of 1, divided by S



#interview_question 
Why do we initialize the weights using random noise, instead of all at 0?
To avoid symmetrical updates in the weights, and force each hidden unit to learn differently.
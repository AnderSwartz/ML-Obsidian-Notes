- Has 1 dim per weight
- a point/vector in weight space has particular value for all the weights
- Every training case can be represented as a hyperplane through the origin in weight space
- For a particular training case, the weights must lie on one side of this hyper=plane to get the correct answer

![[Pasted image 20250119115652.png]]
- each sample is a plane (black line) that goes through origin and is perpendicular to the input vector

good weight vector dotted w/ input vector is pos -> predicts 
bad weight vector dotted w/ input vector is neg



# XOR
![[Pasted image 20250119184706.png]]

This set of training case is not "linearly separable"

with two inputs, a neuron (perceptron) can classify the data points in two-dimensional space into two kinds with a straight line. If you have three inputs, a neuron can classify data points in three-dimensional space into two parts with a flat plane, and so on. This is called "dividing n-dimensional space with a hyperplane."

Add more layers with linear units doesn't help because it can still only learn linearly separable data. "The composition of these linear transformations is itself a linear transformation."


![[Pasted image 20250119191139.png]]
I am hovering over the bottom hidden neuron. The blue region is the feature that hidden unit is representing. See how that bottom connections have a negative weight to the output because it is negatively correlated with the pos class (blue)

# Linear regression weight space
![[Pasted image 20250125160319.png]]
remember, hypothesis is a specific instance of trained params
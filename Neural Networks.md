# General Info
![[Pasted image 20241103204752.png]]
num of input nodes corresponds to number of features
nonlinear activation functions -> non-convex optimizaiton


If X is a 2 vector
If the size of the hidden layer is 2, W is 2x2
Wx is 2x1
so the input to activation function is this vector
if Wx i= s [-1, 2] and h(s) is ReLu, h(s) = [0, 2]
in this case, y is just a number, and w is a vector

so y = h(s)w
if its classification, sigmoid(y) to get a prob
# Activation function


# Backpropagation
![[Pasted image 20241104202436.png]]
L total layers.
l = 0 is the input layers

d = num nodes in layer
i = index of starting node of weight
j = index of ending node of weight

wijl is the weight matrix connect layer l-1 to l
s = weighted sum of wijl * xi(l-1)

output is function of w
define loss function E(w)
![[Pasted image 20241104202813.png]]
minimize loss function w.r.t. w

This is an *unconstrained* optimization problem, which we optimize with stochastic gradient descent, which optimizes to local minimum, not global

![[Pasted image 20241104202934.png]]

# Gradient
![[Pasted image 20241104203054.png]]
# Overfitting

## Dropout
remember that for decision trees, we used ensemble methods to fit multiple models to reduce variance.
Since we can't train multiple NN models (too expensive), we use dropout to mimic this behavior. This is done for each hidden layer when a binary vector exists for each hidden layer to determine if the hidden node in that layer is used or not.
In practice, we define a global prob (such as .2) for any given node to be dropped out. That means at the end of training, each node had a .8 prob of being updated.
During evaluations, this .8 is multiplied by the value of the hidden unit to get its expected value

It randomly switches off (drops out) some of the nodes. This is done for each batch

## Batch Normalization
"covariation happens from layer to layer"
adjust for this transformation by normalizing the data

normalize w.r.t. the cols across the batch, for each layer(?)

as you get more batches, you keep track of a moving avg and sigma for each node

after training, scale the data by the avg and sigma


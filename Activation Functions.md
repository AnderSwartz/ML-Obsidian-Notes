#interview_question Where is non-linearity in NNs?
Just in the activation function!
A linear activation function would reduce the NN to a linear model
Common activation functions: tanh, ReLU, and sigmoid

What is the motivation for having a non-linear function?
If their was no activation function, it would just a linear combination of weights and inputs. Creating multiple layers of such linear combinations would be unnecessary, since they could be collapsed to a single layer. This is exactly the same as how multiple transformations on a vector can be combined into a single matrix. 
y = W(L)W(L−1) · · ·W(1)x. But this could be viewed as a single linear layer with weights given by W = W(L)W(L−1) · · ·W(1). The composition of successive linear transformations is itself a linear transformation


# Binary thresholds
![[Pasted image 20250119110554.png]]

#look_into 
Why is it hard to do gradient descent with hard thresholds

# ReLU
![[Pasted image 20250119111029.png]]

Remember, the activation function is applied after the weighted sum + bias.
In both examples above, the activation function is the piece-wise y = .... part

# Sigmoid / Logistic
![[Pasted image 20250119111217.png]]

These nonlinear activation functions are also non-convex.

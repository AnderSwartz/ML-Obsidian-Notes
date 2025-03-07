We first compute all of the values in a forward pass, and then compute the derivatives in a backward pass.

![[Pasted image 20250304215438.png]]
![[Pasted image 20250304215509.png]]
![[Pasted image 20250304215538.png]]
sum over the index of the child (k)
use that index for the bar term (y)
use that index for the first index in the weight (k)



In vector form:
![[Pasted image 20250304220103.png]]
If W comes first in the forward pass,
![[Pasted image 20250304220140.png]]
the x gets transposed during the backwards pass


# Computational Cost
linear in the number of layers because for every 

the derivatives during backprop involve the derivative of every unit (in Hi) with respect to every unit in Hi-1. Succintly, the derivative of a vector valued function is a jacobian, which is a matrix (quadratic)
"For a multilayer perceptron, this means the cost is linear in the number of layers, quadratic in the number of units per layer."
its linear because for every layer, theres 1 add-mult forward and 2 backward, so its linear in terms of this. 

But for every hidden unit (in a FC layer)
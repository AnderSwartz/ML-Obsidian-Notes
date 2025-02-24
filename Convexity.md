If S is a convex set (or space), any weighted average of elements (or points) in S is also in S.
# Data Space
The positive and negative regions are convex if they can be separated with a line?

If a loss function is convex (in terms of model output), and the model is linear, the loss function is also convex in terms of the model params.

# Hidden units and nonconvexity
You can swap hidden units symmetrically such that the function that is defined by the network is the same, even though the params are different.
![[Pasted image 20250211191121.png]]

#interview_question 
- Just because a loss function is convex w.r.t. the model outputs doesn't mean its convex w.r.t. to the params
	- But because linear models have outputs that are just linear functions of the weights, these loss functions are convex w.r.t the params
	- Even though linear regression is convex, there is no closed-form solution
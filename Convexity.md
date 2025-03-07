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
	- Even though logistic regression is convex, there is no closed-form solution


# Convex sets:
![[Pasted image 20250306224704.png]]
![[Pasted image 20250306224728.png]]

# Convex Functions
A function f is convex if for any x0, x1, f ((1 − λ)x0 + λx1) ≤ (1 − λ)f (x0) + λf (x1)
Used in the context of ML:
J (λ1θ1 +· · ·+λN θN ) ≤ λ1J (θ1) +· · ·+λN J (θN )
![[Pasted image 20250306225246.png]]

For a linear model, z = w>x + b is a linear function of w and b. If the loss function is convex as a function of z, then it is convex as a function of w and b



Counter examples for translation invariance and MLP:
1. Show the same function can be computed by a network with different weights
2. J (λ1θ1 +· · ·+λN θN ) ≤ λ1J (θ1) +· · ·+λN J (θN )
	1. The left side is this averaged weights
	2. This claims averaging the weights must be at least as good as any other configurations
	3. This is obviously false
	4. 
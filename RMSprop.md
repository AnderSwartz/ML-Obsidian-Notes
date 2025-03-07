
sj dappens the step step size when curvature is high
sj magnifies the step size when curvature is low
it evens out the step size so its more consist

it only takes into account terms on the diagonal of the Hessian, but probably don't worry about this

Motivation:
Sometimes we don't want to take big steps just because the curvature is large. In a ravine, this would result in hopping across the ravine instead of going downstream. Put this in better terms ^

when you average over time, there is a question of how much history to use. A small gamma means you only get a small contribution from current gradient.

RMSprop keeps a running avg of your squared gradients

Fundamentally, asks "how consistent are your squared gradients"


This is specific to each param (dim)
- you can be oscillating in some dims but not others
![[Pasted image 20250302101538.png]]
we square the each component in the gradient to get the magnitude, since we don't care about whether its pos or neg. If that magnitude is larger, you are in a point with high curvature??
When gamma is large, you use more of the current gradient and less of the history



![[Pasted image 20250302101142.png]]

Intuition: the squared gradients give an approximation of the curvature.
In low-curvature regions, the squared gradient tends to be smaller, and vice versa

if sj is large (the moving avg of squared gradients) (also, when curvature tends to be large), then the coefficient in front of the gradient gets smaller, and vice versa


# Adagrad
Intuition: in an NLP problem, some features (words) are very uncommon. We want to update the weights associated with these words more than we do for common features (words)
- Adagrad adapts the learning rate for each parameter dynamically, making training efficient for sparse data

The sum from Adagrad would just increase forever.
Replace sum with exp mov avg

Bias correction because the moving avg will be heavily biased by the first value (which is used for the first prev avg value)
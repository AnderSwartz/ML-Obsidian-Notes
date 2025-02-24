![[Pasted image 20250213155736.png]]
p is momentum, and its the new term used to update the weights
μ is the damping param, usually around .9 or .99

The intuition is that p will keep growing in the same direction (pos or neg) as long as the gradient stays the same sign (pos or neg).
As long as the puck is going downhill, it should gain speed

Momentum keeps a running average of your gradient updates
The updates are different for each param (p is a vector)
but the dampening parameter applies to them all the same

Momentum fundamentally asks "how consist have your gradients been?"

contribution of grad from time step t-1 is μp
contribution of grad from time step t-2 is μ^2 p

#interview_question 
Why can't μ >= 1?
if its >= 1, p will never get smaller (in magnitude)
Example: 
grad = 1
μ = 1
p = 1
alpha = 1
1. p = -1
2. p = -2
3. p = -3
4. assume grad = 0
5. p = -3
6. p = -3
Even though grad = 0 (we've arrived at a solution!), we keep updating!

Example 2: 
grad = 1
μ = 1
p = 1
alpha = 1
1. p = -1
2. p = -2
3. p = -3
4. assume grad = -1
5. p = -2
6. p = -1
Even though grad = 0 (we've arrived at a solution!), we keep updating!

# Motivation
- Smooths out noisy gradients
	- Noisy gradients can happen because the gradients from each individual data point (in stochastic or mini-batch gradient descent) can be very different from each other, causing the optimizer to take erratic steps.
	- If the gradient is fluctuating a lot, momentum will smooth it out
- Accelerate gradients if they stay in the same direction

![[Pasted image 20250217174939.png]]


# Exponential Moving Avg
New Average=(β×Previous Avg)+(1−β)×New Temperature
- The "previous avg" term incorporates information from past time steps, but each previous time step contributes exponentially less. 
- EMAt​=(1−β)Tt​+β(1−β)Tt−1​+β^2(1−β)Tt−2​
- to find how each time step contributes, if its 3 back )t-3,  β^3 (1−β)Tt−3​


- β (0 ≤ β ≤ 1) is the smoothing factor, which controls how much weight is given to past values.
    - A higher β makes the average respond **more slowly** to new data.
    - A lower β makes it respond **more quickly** to new data.
# Overshooting problem
the ball has too much momentum and "overshoots" the minimum!
Solution: Nesterov Momentum computes the gradient at an approximated next position


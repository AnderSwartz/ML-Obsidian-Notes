The hessian is the second derivative of a function which describes the local curvature of the function. It tells us if a function _f (x)_ has a saddle point, local minima or maxima at _x._ The hessian is useful only when it is positive definite as this provides a descent direction. **This along with the need to calculate the hessian and its inverse is part of the reason it is not the most used approach.**

The **first-order Taylor approximation** provides a linear function that best approximates f(x) around x0
- L(x)=f(a)+f′(a)(x−a)
- L(x)=f(a)+∇f(a)⋅(x−a)
	- ∇f(a)=(∂x1​∂f​,∂x2​∂f​,...,∂xn​∂f​)​ |x=a​
	- (x−a) is the vector of small changes: 
		- (x1​−a1​,x2​−a2​,...,xn​−an​)
	- In higher dimensions, this is the tangent hyperplane
- ![[Pasted image 20250212212743.png]]


A second-order Taylor approximation is a specific type of quadratic approximation derived from the Taylor series at a point.
![[Pasted image 20250212214233.png]]
- The approximation function, Q_f, has the same value as f at the point f{x0}, all its partial derivatives have the same value as those of f at this point, and all its _second_ partial derivatives have the same value as those of f at this point.
- The dot product $\nabla f(\textbf{x}_0) \cdot (\textbf{x} - \textbf{x}_0)$ will expand into the sum of all terms of the form $f_{x}(\textbf{x}_0)(x - x_0)$ 
- ![[Pasted image 20250212215814.png]]


# Curvature
### Intuition:

- Imagine driving on a hilly road where elevation corresponds to J(θ). The first derivative tells you if you’re going uphill or downhill.
- The second derivative tells you **how sharply** the road is curving—whether it's getting steeper or flattening out.
- High curvature = gradient changing a lot (not consistent) = ravine = momentum dampens oscillations
- Low curvature = gradient changing a little (very consistent) = nearly flat = momentum speeds up param updates
- Each eigenvalue (of H) represents the curvature along a specific eigenvector direction.
	- Positive Eigenvalues → Upward Curvature (Convex)
	    
	    - If all eigenvalues are positive, the function curves **upward in all directions** (local minimum or convex region).
	- Negative Eigenvalues → Downward Curvature (Concave)
	    - If all eigenvalues are negative, the function curves **downward in all directions** (local maximum or concave region).
	- Mixed Signs (Some Positive, Some Negative) → Saddle Point
	    - If the Hessian has both positive and negative eigenvalues, the function curves **up in some directions and down in others**, forming a **saddle point**.
	- Zero Eigenvalues → Flat Directions
	- If an eigenvalue is zero, the function is locally **flat** in that direction.
- Remember, H is a (matrix-valued) function that can be evaluated at any point θ
- Example: L=x^2 -4xy-4
- H = 
[2, -4]
[-4, 0]
- This is indefinite, so it is a saddle point here (positive curvature in some directions, neg in others)
- If this was positive definite, it would have pos curv in all directions = local min
- 


[[Neural Networks]]
A MLP with just one layer and nonlinear activation functions can represent any function
- If D inputs (features), use 2^D hidden units. For each unique input, assuming each feature is binary, there is a single corresponding hidden unit that activates. 
- For example, say I wanted a hidden unit that only activates for input (-1, 1, -1).
	- The weights could be the same as the input (-1, 1, -1) w/ bias -2.5. 
	- Then, the weight b/w that hidden unit and output is whatever you want the output to be

# Problems
- This requires too many weights. Functions will not be represented **compactly**
- Even if this wasn't a problem, universality would just mean that a NN can be learned to perfectly predict the training set by effectively memorizing it

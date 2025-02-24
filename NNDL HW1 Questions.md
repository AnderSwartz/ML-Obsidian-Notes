# 1.1
1. Would you recommend coding this up, creating a dummy dataset, and then learning the weights? Or do we need to mathematically derive the weights? If so, I'm not sure how to go about that.
2. Are we limited to just the two activation functions, or can we use others?

# 1.2
1. This network has skip connections?
	1. It also has g = c1 dot c2, which is element-wise multiplication.  Does this correspond to something we've learned?
2. What is the derivative of ReLU, softmax, and S? Which of these can we just write as σ (sigma) '

# 1.3 
1. Is L a loss, x an input, and v some weights?
2. Taking der with this vector notation
3. 1.3.1 How do we backprop? Normally in backprop, we have loss function and take der w.r.t. weights. in this, what do we do? z is kinda the output of the function, Hy is intermediate, vvTy is end
Allows us to compare models without factoring in threshold.

You can generate the curve after training the model
![[Pasted image 20241009175342.png]]
You can plot PR curves for each threshold and compare them.

At any recall, the precision is better for the orange.

# Average Precision
area under curve. A bigger area is better

This is all for comparing models. Once you go into prod, you still need to set a threshold
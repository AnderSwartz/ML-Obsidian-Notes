
![[Pasted image 20250309152417.png]]
Each output y is the typical hidden layer activation (depends on weights and previous layer) + x. This new part F(x) is the residual. Each layer adds something to the previous layers value.

# Difference b/w RNN and Residual Layers
- RNN has a new input x at each time step
- Residual nets keep using the same x for all layers
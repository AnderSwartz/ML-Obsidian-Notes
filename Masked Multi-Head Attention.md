![[Pasted image 20250325161011.png]]
The masking is to make sure it is causal. We can only attend to previous outputs that we've generated. This is for self-attention in the decoder. You mask out the future words (and their attention)
There is no masking in the encoder (in most cases, unless its live translation?)
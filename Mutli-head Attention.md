Just like in a ConvNet when we had different kernels, [[Transformers]] have multi-head attention where have can have multiple, separate Q, K, V groups for the same sequence

This is why Q, K, and V becomes matrices. "A different vector for every head of attention"


![[Pasted image 20250330194023.png]]
Rightmost side, we split the new Q' along the d_model dimension, so every attention head sees the full sentence, but a smaller part of the embedding of each word.

If d_model (dimensionality of embedding) is 512, it will become 512 / d_k, where d_k is the number of heads. Here, d_k is 4. d_k is d_v in the paper
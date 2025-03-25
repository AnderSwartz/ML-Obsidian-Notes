[[Transformers]]
# Query (Q)

- We are looking for which key matches the Q the best (by using dot product)
- The Q 

# Key (K)
- 1 Key vector associated with every input word
- They are used to get the attention weights

# Value (V)
- 1 Value vector associated with every input word
- Once the attention weights are computed, they are multiplied with the value vector for each input word
The actual annotations from the encoder

This is used to find the **attention values**
# Context
![[Pasted image 20250313175818.png]]
i = output position
j = input position
c = context
a = attention weight
h = annotation
C_i = summing through input word positions, taking product of attention weight connecting input j to output j times the annotation.
C_i is a weighted average of the annotations

put simply, the dot product of q and k gives you a weighting for v. 
The context is simply the sum of these for each input word

# Dot-Product Attention
Doing dot-product of Queries with Keys

1. Dot product QK^T is computed
2. Attention is computed from the Softmax of this dot-product
3. Then, context is computed using just the attention weights and the values.
The context is the final thing

## Scaled Dot-Product Attention
1. Dot product QK^T is computed
2. it is divided by dk, which is the key dimension (same dimension as query)
	If you have a very long dk, the softmax values can become peaked, where some values are very large. This scaling makes the distribution of the softmax (output) similar for different dk
3. Attention is computed from the Softmax of this dot-product
4. Then, context is computed using just the attention weights and the values.
![[Pasted image 20250325151553.png]]
Here, dk is 3 because the key dimension has 3 rows

Each word has a query vector and 
![[Pasted image 20250325145415.png]]
![[Pasted image 20250325145422.png]]

- QK^T is MatMul
- divide by sqr(dk) is scale
- mask is optional dropout
- softmax of the remaining Matrix


# Shapes of Q, K, and V

![[Pasted image 20250325145615.png]]
![[Pasted image 20250325145658.png]]
- dmodel = embedding dimension of model
- L = sequence **length** (number of words / tokens)
- X is shape (L, dmodel)
- In his example below, both L is columns (3) and dmodel is rows 
- dmodel = dl
- ![[Pasted image 20250325150908.png]]


# What is a transformer?
In the same way a ConvNet using Convolution modules, a Transformer model / network uses transformer modules

# 3 forms of attention in Attention is all you need
1. [[Self Attention]] in encoder
2. Self Attention in decoder
3. encoder-decoder attention, where, during decoding to the second language, we pay attention to the word annotations from the encoder (for the first language)


- Each hidden state now has a Q, K, V
- The Q is used for self-attention (if the previous layer is another hidden layer) or encoder-decoder attention (if the current layer is first decoder, previous layer is final encoder layer)
- The K, V get used by the self attention for the next layer (if current layer is hidden, next layer is hidden) or for the encoder-decoder attention (if current layer is final encoder, next layer is first decoder)

Uses [[Mutli-head Attention]]
Uses [[Positional Encoding]]
Paying attention to the hidden states from the last hidden layer
![[Pasted image 20250405191956.png]]
red circle value is dot product of first row of Q and second col of K.T


# Softmax
applied to each row to make sure each row sums to 1


# Final Attention
![[Pasted image 20250405192843.png]]

Now, the first row of the Attention matrix still captures the first row of the word in the sequence, but now with all the special context


- The encoder processes the **entire source sequence** once, producing a fixed-size representation (`keys` and `values`).
    
- The decoder autoregressively generates tokens using:
    
    - The encoder's static output (fixed `seq_len` from source)
        
    - Its own previously predicted tokens (growing `k` steps)
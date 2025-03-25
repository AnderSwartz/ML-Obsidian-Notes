Before in [[Attention]], swapped around the order of words does not change the attention weights for weights for each word. The attention weight for a word is just the dot-product of Q and K (scaled and softmaxed), so the position of the attention score would change, but each word would still have the same attention score.
Then the context is the weighted average of the values and attention scores, which will be the same regardless of the order.
![[Pasted image 20250325154628.png]]

Intuition is that the order should be important. The context should change depending on order of words.

- Every word has a fixed position embedding vector
- The even words use sins, odds use cosines
- Key idea: every word has a unique position embedding, and closeby words have similar position embeddings

Position Encoding 


E original input embedding for entire sequence is shape is shape (L, dmodel)

PE Position Encoding is also (L, dmodel)

Final Embedding X = E + PE
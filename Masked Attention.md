[[Self Attention]]
- For decoder self-attention
- The masking occurs right before the softmax
- After k @ q, we get shape (seq, seq). This is what gives us the attention map
![[Pasted image 20250405193544.png]]

The word of each row "attends to" the words in each col.
In first row, we only want "your" to attend to itself. 
In second row, "cat" can attend to "your" and "cat"


This is all done in parallel on the target sequence.
For example, when the first two words are already predicted, teacher forcing ensures the decoder gets the "your cat" as input. This is why all other words in the second row are masked.

Basically, the decoder is training every possible "task" that can be derived from the sentence in parallel.

At the last masked self-attention layer of the decoder, only the queries are used for the cross-attention. These queries are matched to the keys from the final layer of the encoder


The final self-attention layers queries are all that are used
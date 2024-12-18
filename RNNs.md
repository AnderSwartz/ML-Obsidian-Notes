The one-to-one vocab is also used for input-outputs in ML

Image classification = one to one
image captioning = one to many
sentiment analysis = many to one
machine translation = many to many
RNNs can be used for all of these tasks

In traditional feed-forward NNs, the hidden states are *stateless*. 
this makes them bad at dealing with sequences, because it doesn't know that each input is a sequential time step.

you can take the output after each time step, but often times you don't care about them.
Only take output for last input for sentiment analysis. 
But for named entity recognition (many to many) you can take output after each time step

# What is happening in the cell?

| X^t   | input at time t                         |
| ----- | --------------------------------------- |
| a^t-1 | hidden cell state at previous time step |
| a^t   | hidden cell state at time t             |
# Problems
Long-term dependencies
vanishing/exploding gradients: the gradients get multiplied because of the long sequences (?)

# LSTMs 
Forget gate: determines which info is relevant from the prior steps
lets say your sentence is encoding gender and has been keeping track of "girl" but then the new input contains "boy", it should forget the "girl" encoding
Input gate: decides which info should be added from the current step
output gate: finalize the next hidden state
the goal of all this is to manipulate the cell state

upper line is cell state, which gets update with each new input

#interview_question what is the difference b/w the gates in LSTMs vs GRUs?
LSTMs have 3, GRUs have 2. the "update" gate in GRUs is a combo of the forget and input gate in LSTMs

In recommender systems, they use LSTMnet


#interview_question exploration vs exploitation
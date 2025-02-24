when we move from binary classification to multi-class classification, we use the softmax as an activation function instead of the sigmoid (for the final layer).
This is because the label is OHE. Our last layer output k values where k=number of classes. These values z1,...zk are the *logits* and are inputs to the softmax

Because of some magic in the softmax cross entropy loss, the only value from y (remember, y is a softmaxed vector) that contributes to the loss is the max value (predicted class) 
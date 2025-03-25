We need to store the hidden unit activations for every time step because they will be needed for backprop through time

For [[Transformers]], we backprop for the hidden units in any given layer can be done in parallel
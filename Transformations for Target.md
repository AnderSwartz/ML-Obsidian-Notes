Sometimes if the target variables is highly skewed, you transform it with a function like a logarithmic, square, or cubed function and then predict those transformed targets.

A log transform might only work if all the original targets are positive. Oftentimes, you do multiple transformations (squared, cubed, etc.) and train different models with different targets. Sometimes you can just remove the outliers in the data. 




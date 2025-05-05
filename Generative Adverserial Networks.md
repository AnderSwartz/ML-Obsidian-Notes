[[Generative Models]]
# Potential problems
1. Both models (G and D) can get stuck, resulting in G never improving
2. D can be too good and G never improves
3. G might just memorize the training images
4. G might only generalize to a small section **(a mode)** of the distribution. E.g. a G trained on imagenet its good at generating hamburgers, so it only generates those
5. The D can't tell you if a sample is in the dist. or not. It only give p(real)
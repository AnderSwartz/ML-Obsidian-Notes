The same distribution is then used to generate every train example and every test example. We cal that shared underlying distribution the data generating distribution, denoted pdata. This probabilistic framework and the i.i.d. assumptions alow us to mathematicaly study the relationship between training error and test error. (Goodfellow 126). 

The ideal model is an oracle that simply knows the true probability distribution that generates the data. Even such a model wil stil incur some error on many problems, because there may stil be some noise in the distribution. In the case of supervised learning, the mapping from x to y may be inherently stochastic, or y may be a deterministic function that involves other variables besides those included in x. The error incurred by an oracle making predictions from the true distribution p(x, y) is caled the Bayes error.

(Goodfellow 131). 

The test error at optimal capacity asymptotes to the Bayes error.
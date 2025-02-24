- **Probability** is used when the model and its parameters are known, and we are analyzing possible data outcomes.
- **Likelihood** is used when data is observed, and we are trying to infer the best model parameters
L(θ∣X=x)=P(X=x∣θ)

Likelihood is treated as a function of θ, whereas probability is a function of X

# Example using Binomial
Imagine a coin flips 10 times
N = num trials = 10
k = number of heads
p = p(heads during a single flip)

![[Pasted image 20250203145343.png]]

its N choose k because

"4 choose 2" refers to the number of ways to select 2 items from a set of 4 without considering the order. So, there are **6 ways** to choose 2 items from 4.

For example, if you have elements **{A, B, C, D}**, the possible pairs are:
1. (A, B)
2. (A, C)
3. (A, D)
4. (B, C)
5. (B, D)
6. (C, D)

![[Pasted image 20250203150155.png]]

Using the above binomial equation with p=.5, N=10, here are the various values for p(K=k)

## Likelihood
Is about p(params | data)

here is the probability of different p values (a fair coin is p=.5) given some observed data.
In this example, data is k=7, n=10

See the relationship?
L(θ∣X=x)=P(X=x∣θ)

==What the likelihood function gives us is a== ==_measure_== ==of how likely any particular value of== ==_p_== ==is given that we know that== ==_K_== ==equals some observed value==

Note that here the likelihood function is not symmetrical; rather, it is peaked over _p_ = .7. Specifically, the _mode_ of this distribution (i.e., the peak itself) coincides with something called the _maximum likelihood estimate_ (MLE).

the likelihood function is **not** the probability that _p_ equals a particular value (for that you’ll need to compute the posterior distribution

- You know the parameters `σ, μ` of the distribution, you call it "the probability density function" and you write it as `f(x | μ, σ)`. You use it to predict future outcomes for the random variable `X`.
    
- You don't know the parameters `σ, μ`, you call it "the likelihood function" and you write it as `L(μ, σ | x)`. It helps in finding the most plausible values of `μ, σ` given a set of observed/known outcomes of `X` via what is called the "maximum likelihood estimation"
# Calculating MLE
Say we have observed some data and now want to find the params that are most likely to have generated the data. We do through through MLE.


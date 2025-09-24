# Hypergeometric Distribution

The hypergeometric distribution models the probability of drawing a specific number of successes in draws without replacement from a finite population.

## Parameters
- N: Total population size
- K: Number of successes in population  
- n: Number of draws
- k: Number of observed successes

## Probability Mass Function
P(X = k) = C(K,k) * C(N-K,n-k) / C(N,n)

## Properties
- Mean: μ = n * K/N
- Variance: σ² = n * (K/N) * (1 - K/N) * (N-n)/(N-1)

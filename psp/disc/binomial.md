# Binomial Distribution

## Definition
The binomial distribution models the number of successes in n independent Bernoulli trials, each with the same probability p of success.

## Probability Mass Function (PMF)
For a binomial random variable X with parameters n and p:

**P(X = k) = C(n,k) × p^k × (1-p)^(n-k)**

Where:
- k = number of successes (k = 0, 1, 2, ..., n)
- n = number of trials
- p = probability of success in each trial
- C(n,k) = n!/(k!(n-k)!) = binomial coefficient

## Mean (Expected Value)
**Derivation:**
E[X] = Σ k × P(X = k) for k = 0 to n
     = Σ k × C(n,k) × p^k × (1-p)^(n-k)

Using the identity: k × C(n,k) = n × C(n-1,k-1)

E[X] = Σ n × C(n-1,k-1) × p^k × (1-p)^(n-k)
     = np × Σ C(n-1,k-1) × p^(k-1) × (1-p)^(n-k)
     = np × (p + (1-p))^(n-1)
     = np × 1
     = np

**Result: μ = np**

## Variance
**Derivation:**
Var(X) = E[X²] - (E[X])²

First, find E[X²]:
E[X²] = E[X(X-1)] + E[X]

E[X(X-1)] = Σ k(k-1) × C(n,k) × p^k × (1-p)^(n-k)

Using the identity: k(k-1) × C(n,k) = n(n-1) × C(n-2,k-2)

E[X(X-1)] = n(n-1)p² × Σ C(n-2,k-2) × p^(k-2) × (1-p)^(n-k)
          = n(n-1)p² × (p + (1-p))^(n-2)
          = n(n-1)p²

Therefore:
E[X²] = n(n-1)p² + np
        = n²p² - np² + np
        = n²p² + np(1-p)

Var(X) = E[X²] - (E[X])²
       = n²p² + np(1-p) - (np)²
       = n²p² + np(1-p) - n²p²
       = np(1-p)

**Result: σ² = np(1-p)**

## Standard Deviation
**σ = √(np(1-p))**

## Moment Generating Function
**M(t) = E[e^(tX)] = (1-p+pe^t)^n**

## Properties
1. **Support**: {0, 1, 2, ..., n}
2. **Parameters**: 
   - n ∈ {1, 2, 3, ...} (number of trials)
   - p ∈ [0, 1] (probability of success)
3. **Mode**: 
   - floor((n+1)p) if (n+1)p is not an integer
   - Both floor((n+1)p) and floor((n+1)p)-1 if (n+1)p is an integer
4. **Skewness**: (1-2p)/√(np(1-p))
5. **Kurtosis**: 3 + (1-6p(1-p))/(np(1-p))

## Special Cases
- When n = 1: Binomial reduces to Bernoulli distribution
- When n is large and p is small: Binomial approximates Poisson distribution (np = λ)
- When n is large: Binomial approximates Normal distribution by Central Limit Theorem

## Example Problems

### Example 1: Coin Flipping
**Problem**: A fair coin is flipped 10 times. Find the probability of getting exactly 6 heads, and calculate mean and variance.

**Solution**:
- Parameters: n = 10, p = 0.5
- P(X = 6) = C(10,6) × (0.5)^6 × (0.5)^4
           = 210 × (0.5)^10
           = 210 × (1/1024)
           = 210/1024 ≈ 0.205
- Mean: μ = np = 10 × 0.5 = 5
- Variance: σ² = np(1-p) = 10 × 0.5 × 0.5 = 2.5
- Standard deviation: σ = √2.5 ≈ 1.58

### Example 2: Quality Control
**Problem**: A manufacturing process has a 2% defect rate. In a batch of 100 items, what's the probability of finding exactly 3 defective items?

**Solution**:
- Parameters: n = 100, p = 0.02
- P(X = 3) = C(100,3) × (0.02)^3 × (0.98)^97
           = 161,700 × 0.000008 × 0.132
           ≈ 0.180
- Mean: μ = np = 100 × 0.02 = 2
- Variance: σ² = np(1-p) = 100 × 0.02 × 0.98 = 1.96
- Standard deviation: σ = √1.96 = 1.4

### Example 3: Medical Testing
**Problem**: A drug has 80% success rate. If administered to 15 patients, what's the probability that at least 12 will recover?

**Solution**:
- Parameters: n = 15, p = 0.8
- P(X ≥ 12) = P(X = 12) + P(X = 13) + P(X = 14) + P(X = 15)

P(X = 12) = C(15,12) × (0.8)^12 × (0.2)^3 = 455 × 0.0687 × 0.008 ≈ 0.250
P(X = 13) = C(15,13) × (0.8)^13 × (0.2)^2 = 105 × 0.055 × 0.04 ≈ 0.231
P(X = 14) = C(15,14) × (0.8)^14 × (0.2)^1 = 15 × 0.044 × 0.2 ≈ 0.132
P(X = 15) = C(15,15) × (0.8)^15 × (0.2)^0 = 1 × 0.035 × 1 ≈ 0.035

P(X ≥ 12) ≈ 0.250 + 0.231 + 0.132 + 0.035 ≈ 0.648

- Mean: μ = np = 15 × 0.8 = 12
- Variance: σ² = np(1-p) = 15 × 0.8 × 0.2 = 2.4
- Standard deviation: σ = √2.4 ≈ 1.55

## Applications
1. **Quality Control**: Number of defective items in a batch
2. **Medicine**: Number of patients recovering from treatment
3. **Marketing**: Number of customers making purchases
4. **Finance**: Number of successful investments
5. **Sports**: Number of wins in a series of games
6. **Genetics**: Number of offspring with certain traits

## Relationship to Other Distributions
1. **Bernoulli**: Special case when n = 1
2. **Poisson**: Approximation when n is large, p is small (np = λ)
3. **Normal**: Approximation when n is large (Central Limit Theorem)
4. **Hypergeometric**: Similar but sampling without replacement
5. **Negative Binomial**: Models number of trials until r successes

## Approximations
1. **Poisson Approximation**: When n ≥ 20 and p ≤ 0.05, or n ≥ 100 and np ≤ 10
2. **Normal Approximation**: When np ≥ 5 and n(1-p) ≥ 5
   - Use continuity correction: P(X = k) ≈ P(k-0.5 < Y < k+0.5) where Y ~ N(np, np(1-p))

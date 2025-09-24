# Poisson Distribution

## Definition
The Poisson distribution models the number of events occurring in a fixed interval of time or space, given that events occur independently at a constant average rate.

## Probability Mass Function (PMF)
For a Poisson random variable X with parameter λ:

**P(X = k) = (e^(-λ) × λ^k) / k!**

Where:
- k = number of events (k = 0, 1, 2, 3, ...)
- λ = average rate of occurrence (lambda > 0)
- e = Euler's number (≈ 2.71828)

## Mean (Expected Value)
**Derivation:**
E[X] = Σ k × P(X = k) for k = 0 to ∞
     = Σ k × (e^(-λ) × λ^k) / k!
     = e^(-λ) × Σ k × λ^k / k!
     = e^(-λ) × Σ λ^k / (k-1)!  (for k ≥ 1)
     = e^(-λ) × λ × Σ λ^(k-1) / (k-1)!
     = e^(-λ) × λ × e^(λ)
     = λ

**Result: μ = λ**

## Variance
**Derivation:**
Var(X) = E[X²] - (E[X])²

First, find E[X²]:
E[X²] = E[X(X-1)] + E[X]

E[X(X-1)] = Σ k(k-1) × (e^(-λ) × λ^k) / k!
          = e^(-λ) × Σ k(k-1) × λ^k / k!
          = e^(-λ) × Σ λ^k / (k-2)!  (for k ≥ 2)
          = e^(-λ) × λ² × Σ λ^(k-2) / (k-2)!
          = e^(-λ) × λ² × e^(λ)
          = λ²

Therefore:
E[X²] = λ² + λ

Var(X) = E[X²] - (E[X])²
       = λ² + λ - λ²
       = λ

**Result: σ² = λ**

## Standard Deviation
**σ = √λ**

## Moment Generating Function
**M(t) = E[e^(tX)] = e^(λ(e^t - 1))**

## Properties
1. **Support**: {0, 1, 2, 3, ...}
2. **Parameter**: λ > 0 (rate parameter)
3. **Mode**: 
   - floor(λ) if λ is not an integer
   - Both floor(λ) and floor(λ)-1 if λ is an integer
4. **Skewness**: 1/√λ
5. **Kurtosis**: 3 + 1/λ
6. **Unique Property**: Mean = Variance = λ

## Poisson Process
A Poisson process is a counting process where:
1. Events occur independently
2. The probability of an event in a small interval is proportional to the interval length
3. The probability of more than one event in a small interval is negligible

## Example Problems

### Example 1: Call Center
**Problem**: A call center receives an average of 3 calls per minute. What's the probability of receiving exactly 5 calls in a given minute?

**Solution**:
- Parameter: λ = 3 calls/minute
- P(X = 5) = (e^(-3) × 3^5) / 5!
           = (0.0498 × 243) / 120
           = 12.099 / 120
           ≈ 0.101
- Mean: μ = λ = 3
- Variance: σ² = λ = 3
- Standard deviation: σ = √3 ≈ 1.73

### Example 2: Traffic Accidents
**Problem**: A highway experiences an average of 2 accidents per day. What's the probability of having no accidents on a given day? What about having more than 3 accidents?

**Solution**:
- Parameter: λ = 2 accidents/day
- P(X = 0) = (e^(-2) × 2^0) / 0!
           = e^(-2) × 1 / 1
           = 0.1353
           ≈ 13.53%

- P(X > 3) = 1 - P(X ≤ 3)
           = 1 - [P(X=0) + P(X=1) + P(X=2) + P(X=3)]

P(X=0) = 0.1353
P(X=1) = (e^(-2) × 2^1) / 1! = 0.1353 × 2 = 0.2706
P(X=2) = (e^(-2) × 2^2) / 2! = 0.1353 × 4 / 2 = 0.2706
P(X=3) = (e^(-2) × 2^3) / 3! = 0.1353 × 8 / 6 = 0.1804

P(X ≤ 3) = 0.1353 + 0.2706 + 0.2706 + 0.1804 = 0.8569
P(X > 3) = 1 - 0.8569 = 0.1431 ≈ 14.31%

### Example 3: Manufacturing Defects
**Problem**: A factory produces items with an average of 1.5 defects per 100 items. In a batch of 200 items, what's the expected number of defects and the probability of finding exactly 3 defects?

**Solution**:
- For 200 items: λ = 1.5 × 2 = 3 defects
- Expected defects: E[X] = λ = 3
- P(X = 3) = (e^(-3) × 3^3) / 3!
           = (0.0498 × 27) / 6
           = 1.345 / 6
           ≈ 0.224
- Variance: σ² = 3
- Standard deviation: σ = √3 ≈ 1.73

## Applications
1. **Telecommunications**: Number of phone calls, emails, or network packets
2. **Traffic Engineering**: Vehicle arrivals, accidents
3. **Quality Control**: Number of defects in manufacturing
4. **Biology**: Mutations, cell divisions, radioactive decay
5. **Finance**: Number of defaults, market crashes
6. **Queueing Theory**: Customer arrivals at service centers
7. **Epidemiology**: Disease outbreaks, infection rates

## Relationship to Other Distributions
1. **Binomial**: Poisson is the limit of Binomial as n → ∞, p → 0, with np = λ
2. **Exponential**: Time between Poisson events follows Exponential distribution
3. **Gamma**: Sum of k independent Poisson(λ) follows Gamma(k, λ)
4. **Normal**: For large λ, Poisson approximates Normal(λ, λ)
5. **Compound Poisson**: Generalizes Poisson for varying event sizes

## Approximations
1. **Binomial Approximation**: When n ≥ 20, p ≤ 0.05, and np ≤ 10
   - Use Poisson(λ = np) instead of Binomial(n, p)
2. **Normal Approximation**: When λ ≥ 10
   - Use Normal(λ, λ) with continuity correction
   - P(X = k) ≈ P(k-0.5 < Y < k+0.5) where Y ~ N(λ, λ)

## Poisson Processes in Different Contexts

### Temporal Poisson Process
- Events occur over time
- Example: Customer arrivals, system failures

### Spatial Poisson Process
- Events occur over space
- Example: Stars in a galaxy, defects on a surface

### Compound Poisson Process
- Each event has an associated random "size"
- Example: Insurance claims (frequency and amount)

## Key Formulas Summary
- **PMF**: P(X = k) = (e^(-λ) × λ^k) / k!
- **Mean**: μ = λ
- **Variance**: σ² = λ
- **Standard Deviation**: σ = √λ
- **MGF**: M(t) = e^(λ(e^t - 1))
- **Skewness**: 1/√λ
- **Kurtosis**: 3 + 1/λ

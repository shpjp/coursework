# Bernoulli Distribution

## Definition
The Bernoulli distribution is a discrete probability distribution that models a single trial with two possible outcomes: success (1) and failure (0).

## Probability Mass Function (PMF)
For a Bernoulli random variable X with parameter p:

**P(X = k) = p^k * (1-p)^(1-k)**

Where:
- k ∈ {0, 1}
- p = probability of success (0 ≤ p ≤ 1)
- 1-p = probability of failure

Specifically:
- P(X = 1) = p
- P(X = 0) = 1-p

## Mean (Expected Value)
**Derivation:**
E[X] = Σ k * P(X = k)
     = 0 * P(X = 0) + 1 * P(X = 1)
     = 0 * (1-p) + 1 * p
     = p

**Result: μ = p**

## Variance
**Derivation:**
Var(X) = E[X²] - (E[X])²

First, find E[X²]:
E[X²] = Σ k² * P(X = k)
      = 0² * P(X = 0) + 1² * P(X = 1)
      = 0 * (1-p) + 1 * p
      = p

Therefore:
Var(X) = E[X²] - (E[X])²
       = p - p²
       = p(1-p)

**Result: σ² = p(1-p)**

## Standard Deviation
**σ = √(p(1-p))**

## Moment Generating Function
**M(t) = E[e^(tX)] = (1-p) + pe^t**

## Properties
1. **Support**: {0, 1}
2. **Parameter**: p ∈ [0, 1]
3. **Mode**: 
   - 0 if p < 0.5
   - 1 if p > 0.5
   - Both 0 and 1 if p = 0.5
4. **Skewness**: (1-2p)/√(p(1-p))
5. **Kurtosis**: (1-6p(1-p))/(p(1-p))

## Example Problems

### Example 1: Coin Flip
**Problem**: A fair coin is flipped. Find the probability of getting heads, mean, and variance.

**Solution**:
- Parameter: p = 0.5 (fair coin)
- P(Heads) = P(X = 1) = 0.5
- P(Tails) = P(X = 0) = 0.5
- Mean: μ = p = 0.5
- Variance: σ² = p(1-p) = 0.5(0.5) = 0.25
- Standard deviation: σ = √0.25 = 0.5

### Example 2: Manufacturing Defect
**Problem**: A manufacturing process produces defective items with probability 0.03. If we select one item, what's the probability it's defective? Calculate mean and variance.

**Solution**:
- Parameter: p = 0.03
- P(Defective) = P(X = 1) = 0.03
- P(Not defective) = P(X = 0) = 0.97
- Mean: μ = 0.03
- Variance: σ² = 0.03(0.97) = 0.0291
- Standard deviation: σ = √0.0291 ≈ 0.1706

### Example 3: Medical Test
**Problem**: A medical test has 85% accuracy. Model a single test result.

**Solution**:
- Parameter: p = 0.85
- P(Correct) = P(X = 1) = 0.85
- P(Incorrect) = P(X = 0) = 0.15
- Mean: μ = 0.85
- Variance: σ² = 0.85(0.15) = 0.1275
- Standard deviation: σ = √0.1275 ≈ 0.357

## Applications
1. **Quality Control**: Modeling pass/fail tests
2. **Medicine**: Success/failure of treatments
3. **Finance**: Default/no-default events
4. **Sports**: Win/loss outcomes
5. **Marketing**: Purchase/no-purchase decisions

## Relationship to Other Distributions
1. **Binomial**: Bernoulli is a special case of Binomial with n=1
2. **Geometric**: Models number of Bernoulli trials until first success
3. **Negative Binomial**: Models number of failures before r successes

# Chebyshev's Inequality

## Statement
For any random variable X with finite mean μ and finite variance σ², and for any k > 0:

**P(|X - μ| ≥ kσ) ≤ 1/k²**

Equivalently:
**P(|X - μ| < kσ) ≥ 1 - 1/k²**

## Alternative Forms

### Form 1: With absolute deviation
**P(|X - μ| ≥ ε) ≤ σ²/ε²**

where ε > 0 is any positive number.

### Form 2: Probability within k standard deviations
**P(μ - kσ ≤ X ≤ μ + kσ) ≥ 1 - 1/k²**

### Form 3: One-sided version (Cantelli's inequality)
**P(X - μ ≥ kσ) ≤ 1/(1 + k²)**

## Proof
**Proof using Markov's inequality:**

Let Y = (X - μ)². Then Y ≥ 0 and E[Y] = Var(X) = σ².

For any ε > 0, the event {|X - μ| ≥ ε} is equivalent to {Y ≥ ε²}.

By Markov's inequality:
P(Y ≥ ε²) ≤ E[Y]/ε² = σ²/ε²

Therefore:
P(|X - μ| ≥ ε) ≤ σ²/ε²

Setting ε = kσ gives:
P(|X - μ| ≥ kσ) ≤ σ²/(kσ)² = 1/k² ∎

## Key Properties

1. **Distribution-free**: Applies to any distribution with finite mean and variance
2. **Universal bound**: Provides bounds without knowing the specific distribution
3. **Sharp for some distributions**: The bound is tight for certain distributions
4. **Monotonic**: As k increases, the upper bound on probability decreases
5. **Symmetric**: Bounds both tails equally

## Common Values

| k | Upper bound P(|X-μ| ≥ kσ) | Lower bound P(|X-μ| < kσ) |
|---|---|---|
| 1 | ≤ 1 (100%) | ≥ 0 (0%) |
| 1.5 | ≤ 0.444 (44.4%) | ≥ 0.556 (55.6%) |
| 2 | ≤ 0.25 (25%) | ≥ 0.75 (75%) |
| 3 | ≤ 0.111 (11.1%) | ≥ 0.889 (88.9%) |
| 4 | ≤ 0.0625 (6.25%) | ≥ 0.9375 (93.75%) |
| 5 | ≤ 0.04 (4%) | ≥ 0.96 (96%) |

## Comparison with Normal Distribution

For the standard normal distribution:

| k | Chebyshev bound | Normal (exact) | Efficiency |
|---|---|---|---|
| 2 | ≤ 25% | 4.6% | 18.4% |
| 3 | ≤ 11.1% | 0.3% | 2.7% |
| 4 | ≤ 6.25% | 0.006% | 0.1% |

The bound becomes less tight for larger k values.

## Examples

### Example 1: Student Test Scores
**Problem**: Test scores have mean 75 and standard deviation 10. What's the minimum percentage of students scoring between 55 and 95?

**Solution**:
- μ = 75, σ = 10
- Range: [55, 95] = [μ - 2σ, μ + 2σ]
- k = 2

P(55 ≤ X ≤ 95) = P(|X - 75| ≤ 20)
                   = P(|X - μ| ≤ 2σ)
                   ≥ 1 - 1/2²
                   = 1 - 1/4
                   = 0.75

**Answer**: At least 75% of students score between 55 and 95.

### Example 2: Manufacturing Process
**Problem**: A manufacturing process produces items with mean weight 100g and variance 25g². Find the maximum probability that an item weighs outside [85g, 115g].

**Solution**:
- μ = 100g, σ² = 25g², so σ = 5g
- Range: [85, 115] = [100 - 15, 100 + 15] = [μ - 3σ, μ + 3σ]
- k = 3

P(X < 85 or X > 115) = P(|X - 100| > 15)
                      = P(|X - μ| > 3σ)
                      ≤ 1/3²
                      = 1/9
                      ≈ 0.111

**Answer**: At most 11.1% of items weigh outside [85g, 115g].

### Example 3: Investment Returns
**Problem**: An investment has expected return 8% with standard deviation 12%. What's the minimum probability that the return is between -16% and 32%?

**Solution**:
- μ = 8%, σ = 12%
- Range: [-16%, 32%] = [8% - 24%, 8% + 24%] = [μ - 2σ, μ + 2σ]
- k = 2

P(-16% ≤ X ≤ 32%) ≥ 1 - 1/2² = 1 - 1/4 = 0.75

**Answer**: At least 75% probability of return between -16% and 32%.

## Applications

1. **Quality Control**: Bounding defect rates without knowing exact distribution
2. **Finance**: Risk assessment and portfolio bounds
3. **Statistics**: Sample size determination and confidence intervals
4. **Engineering**: Reliability analysis and tolerance design
5. **Machine Learning**: Generalization bounds and algorithm analysis
6. **Operations Research**: Capacity planning and resource allocation

## Limitations

1. **Conservative bounds**: Often much looser than distribution-specific bounds
2. **Requires finite variance**: Cannot be applied if variance is infinite
3. **Symmetric bounds**: May not be optimal for skewed distributions
4. **Less useful for extreme events**: Bounds become very loose for large k

## Extensions and Variations

### Cantelli's Inequality (One-sided)
For any t > 0:
**P(X - μ ≥ t) ≤ σ²/(σ² + t²)**

Or equivalently:
**P(X - μ ≥ kσ) ≤ 1/(1 + k²)**

### Paley-Zygmund Inequality
For non-negative random variable X with E[X] > 0:
**P(X ≥ θE[X]) ≥ (1-θ)² × (E[X])²/E[X²]**

for 0 < θ < 1.

### Bennett's Inequality
For bounded random variables, provides tighter bounds than Chebyshev.

### Hoeffding's Inequality
For sums of bounded independent random variables.

## Multivariate Chebyshev
For random vector **X** with mean **μ** and covariance matrix **Σ**:

**P((**X** - **μ**)ᵀ**Σ**⁻¹(**X** - **μ**) ≥ k²) ≤ p/k²**

where p is the dimension of **X**.

## Sharpness of the Bound

The Chebyshev bound is sharp for the following distribution:
- P(X = μ + kσ) = 1/(2k²)
- P(X = μ - kσ) = 1/(2k²)
- P(X = μ) = 1 - 1/k²

This shows that the bound cannot be improved in general.

## Relationship to Other Inequalities

1. **Markov's Inequality**: Chebyshev is derived from Markov
2. **Weak Law of Large Numbers**: Follows from Chebyshev's inequality
3. **Central Limit Theorem**: Related convergence concepts
4. **Concentration Inequalities**: Chebyshev is a basic concentration bound

## Practical Guidelines

1. **Use when distribution is unknown**: Main advantage of Chebyshev
2. **Consider alternatives for known distributions**: Normal, exponential bounds
3. **Combine with other information**: Use as baseline, refine with additional data
4. **Sample size planning**: Conservative estimates for required samples
5. **Robust analysis**: Worst-case scenario planning

## Historical Note

Named after Russian mathematician Pafnuty Chebyshev (1821-1894), who proved it in 1867. The inequality is also known as the Bienaymé-Chebyshev inequality, acknowledging Irénée-Jules Bienaymé's earlier work.

## Key Formulas Summary

- **Basic form**: P(|X - μ| ≥ kσ) ≤ 1/k²
- **Complement**: P(|X - μ| < kσ) ≥ 1 - 1/k²
- **General form**: P(|X - μ| ≥ ε) ≤ σ²/ε²
- **One-sided (Cantelli)**: P(X - μ ≥ kσ) ≤ 1/(1 + k²)
- **Multivariate**: P((**X** - **μ**)ᵀ**Σ**⁻¹(**X** - **μ**) ≥ k²) ≤ p/k²

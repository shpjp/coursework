# Normal Distribution (Gaussian Distribution)

## Definition
The normal distribution, also called the Gaussian distribution, is a continuous probability distribution that is symmetric about its mean, with most data concentrated around the center and decreasing toward the tails.

## Probability Density Function (PDF)
For a normal random variable X with parameters μ and σ:

**f(x) = (1/(σ√(2π))) × e^(-(x-μ)²/(2σ²))**

Where:
- x ∈ (-∞, +∞)
- μ = mean (location parameter)
- σ > 0 = standard deviation (scale parameter)
- σ² = variance

## Standard Normal Distribution
When μ = 0 and σ = 1, it's called the **standard normal distribution**:

**φ(z) = (1/√(2π)) × e^(-z²/2)**

## Mean (Expected Value)
**Derivation:**
E[X] = ∫_{-∞}^{∞} x × f(x) dx
     = ∫_{-∞}^{∞} x × (1/(σ√(2π))) × e^(-(x-μ)²/(2σ²)) dx

Using substitution u = (x-μ)/σ, x = μ + σu:
E[X] = ∫_{-∞}^{∞} (μ + σu) × (1/√(2π)) × e^(-u²/2) du
     = μ ∫_{-∞}^{∞} (1/√(2π)) × e^(-u²/2) du + σ ∫_{-∞}^{∞} u × (1/√(2π)) × e^(-u²/2) du
     = μ × 1 + σ × 0  (first integral = 1, second = 0 by symmetry)
     = μ

**Result: E[X] = μ**

## Variance
**Derivation:**
Var(X) = E[(X-μ)²]
       = ∫_{-∞}^{∞} (x-μ)² × f(x) dx
       = ∫_{-∞}^{∞} (x-μ)² × (1/(σ√(2π))) × e^(-(x-μ)²/(2σ²)) dx

Using substitution u = (x-μ)/σ:
Var(X) = σ² ∫_{-∞}^{∞} u² × (1/√(2π)) × e^(-u²/2) du
       = σ² × 1  (using integration by parts)
       = σ²

**Result: Var(X) = σ²**

## Standard Deviation
**σ = √(σ²) = σ**

## Moment Generating Function
**M(t) = E[e^(tX)] = e^(μt + σ²t²/2)**

## Properties
1. **Support**: (-∞, +∞)
2. **Parameters**: 
   - μ ∈ (-∞, +∞) (mean)
   - σ > 0 (standard deviation)
3. **Mode**: μ
4. **Median**: μ
5. **Skewness**: 0 (perfectly symmetric)
6. **Kurtosis**: 3 (mesokurtic)
7. **Inflection points**: μ ± σ

## 68-95-99.7 Rule (Empirical Rule)
- Approximately 68% of data falls within μ ± σ
- Approximately 95% of data falls within μ ± 2σ
- Approximately 99.7% of data falls within μ ± 3σ

## Standardization (Z-score)
To convert any normal distribution to standard normal:

**Z = (X - μ)/σ**

Where Z ~ N(0,1)

## Example Problems

### Example 1: IQ Scores
**Problem**: IQ scores are normally distributed with μ = 100 and σ = 15. Find the probability that a randomly selected person has an IQ between 85 and 115.

**Solution**:
- Given: X ~ N(100, 15²)
- Find: P(85 < X < 115)

Standardize:
Z₁ = (85 - 100)/15 = -1
Z₂ = (115 - 100)/15 = 1

P(85 < X < 115) = P(-1 < Z < 1) = Φ(1) - Φ(-1) = 0.8413 - 0.1587 = 0.6826

Answer: Approximately 68.26%

### Example 2: Manufacturing Process
**Problem**: A manufacturing process produces bolts with lengths normally distributed with μ = 5.0 cm and σ = 0.1 cm. What percentage of bolts will be rejected if specifications require lengths between 4.8 and 5.2 cm?

**Solution**:
- Given: X ~ N(5.0, 0.1²)
- Find: P(X < 4.8 or X > 5.2) = 1 - P(4.8 ≤ X ≤ 5.2)

Standardize:
Z₁ = (4.8 - 5.0)/0.1 = -2
Z₂ = (5.2 - 5.0)/0.1 = 2

P(4.8 ≤ X ≤ 5.2) = P(-2 ≤ Z ≤ 2) = Φ(2) - Φ(-2) = 0.9772 - 0.0228 = 0.9544

P(rejection) = 1 - 0.9544 = 0.0456

Answer: Approximately 4.56% will be rejected

### Example 3: Investment Returns
**Problem**: Stock returns are normally distributed with μ = 8% and σ = 12%. What is the probability of a loss (negative return)?

**Solution**:
- Given: X ~ N(8, 12²)
- Find: P(X < 0)

Standardize:
Z = (0 - 8)/12 = -0.667

P(X < 0) = P(Z < -0.667) = Φ(-0.667) ≈ 0.2525

Answer: Approximately 25.25% probability of loss

## Applications
1. **Psychology**: IQ scores, test scores
2. **Manufacturing**: Quality control, measurement errors
3. **Finance**: Stock returns, risk modeling
4. **Biology**: Heights, weights, blood pressure
5. **Physics**: Measurement errors, random noise
6. **Economics**: Income distribution (log-normal)
7. **Statistics**: Sampling distributions, confidence intervals

## Central Limit Theorem
The sum (or average) of many independent random variables, regardless of their individual distributions, approaches a normal distribution as the sample size increases.

**If X₁, X₂, ..., Xₙ are independent with mean μ and variance σ², then:**

**(X̄ - μ)/(σ/√n) → N(0,1) as n → ∞**

## Relationship to Other Distributions
1. **Chi-square**: If Z ~ N(0,1), then Z² ~ χ²(1)
2. **Student's t**: Arises when estimating mean with unknown variance
3. **F-distribution**: Ratio of two chi-square distributions
4. **Log-normal**: If ln(X) ~ N(μ,σ²), then X follows log-normal
5. **Bivariate Normal**: Extension to two variables

## Special Cases and Approximations
1. **Binomial Approximation**: When n is large, Binomial(n,p) ≈ N(np, np(1-p))
2. **Poisson Approximation**: When λ is large, Poisson(λ) ≈ N(λ, λ)
3. **Standard Normal**: N(0,1) is the foundation for all normal distributions

## Computational Notes
1. **No closed-form CDF**: Must use numerical integration or tables
2. **Error Function**: Φ(z) = 0.5[1 + erf(z/√2)]
3. **Inverse Normal**: Used for generating normal random variables

## Quality Control Applications

### Control Charts
- **3-sigma limits**: μ ± 3σ contain 99.7% of data
- **Process capability**: Cp = (USL - LSL)/(6σ)
- **Six Sigma**: 3.4 defects per million opportunities

### Acceptance Sampling
- **Specification limits**: Define acceptable range
- **Process performance**: Pp, Ppk indices
- **Yield calculation**: Percentage within specifications

## Advanced Topics

### Multivariate Normal
- **Bivariate**: f(x,y) with correlation ρ
- **General case**: X ~ Nₚ(μ, Σ) for p-dimensional vector
- **Marginal distributions**: Each component is normal
- **Conditional distributions**: Also normal

### Transformations
- **Linear transformation**: If Y = aX + b, then Y ~ N(aμ + b, a²σ²)
- **Sum of normals**: X + Y ~ N(μₓ + μᵧ, σₓ² + σᵧ² + 2Cov(X,Y))
- **Independence**: If independent, Cov(X,Y) = 0

## Key Formulas Summary
- **PDF**: f(x) = (1/(σ√(2π))) × e^(-(x-μ)²/(2σ²))
- **Mean**: μ
- **Variance**: σ²
- **Standard Deviation**: σ
- **MGF**: M(t) = e^(μt + σ²t²/2)
- **Standardization**: Z = (X - μ)/σ
- **68-95-99.7 Rule**: 68% within ±σ, 95% within ±2σ, 99.7% within ±3σ

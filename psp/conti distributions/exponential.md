# Exponential Distribution

## Definition
The exponential distribution models the time between events in a Poisson process, representing the waiting time until the next event occurs. It is a continuous probability distribution with a "memoryless" property.

## Probability Density Function (PDF)
For an exponential random variable X with parameter λ:

**f(x) = λe^(-λx) for x ≥ 0**
**f(x) = 0 for x < 0**

Where:
- x ≥ 0 (support)
- λ > 0 (rate parameter)

## Cumulative Distribution Function (CDF)
**F(x) = P(X ≤ x) = 1 - e^(-λx) for x ≥ 0**
**F(x) = 0 for x < 0**

## Mean (Expected Value)
**Derivation:**
E[X] = ∫₀⁾ x × λe^(-λx) dx

Using integration by parts with u = x, dv = λe^(-λx)dx:
du = dx, v = -e^(-λx)

E[X] = [x × (-e^(-λx))]₀⁾ - ∫₀⁾ (-e^(-λx)) dx
     = 0 - (-1/λ) ∫₀⁾ λe^(-λx) dx
     = (1/λ) × 1
     = 1/λ

**Result: E[X] = 1/λ**

## Variance
**Derivation:**
Var(X) = E[X²] - (E[X])²

First, find E[X²]:
E[X²] = ∫₀⁾ x² × λe^(-λx) dx

Using integration by parts twice:
E[X²] = 2/λ²

Therefore:
Var(X) = E[X²] - (E[X])²
       = 2/λ² - (1/λ)²
       = 2/λ² - 1/λ²
       = 1/λ²

**Result: Var(X) = 1/λ²**

## Standard Deviation
**σ = √(1/λ²) = 1/λ**

## Moment Generating Function
**M(t) = E[e^(tX)] = λ/(λ - t) for t < λ**

## Properties
1. **Support**: [0, +∞)
2. **Parameter**: λ > 0 (rate parameter)
3. **Mode**: 0
4. **Median**: ln(2)/λ ≈ 0.693/λ
5. **Skewness**: 2 (right-skewed)
6. **Kurtosis**: 9
7. **Memoryless Property**: P(X > s+t | X > s) = P(X > t)

## Memoryless Property
The exponential distribution is the only continuous distribution with the memoryless property:

**P(X > s+t | X > s) = P(X > t)**

This means the probability of waiting an additional t time units does not depend on how long we've already waited.

**Proof:**
P(X > s+t | X > s) = P(X > s+t ∩ X > s) / P(X > s)
                   = P(X > s+t) / P(X > s)
                   = e^(-λ(s+t)) / e^(-λs)
                   = e^(-λt)
                   = P(X > t)

## Alternative Parameterizations
1. **Rate parameter λ**: f(x) = λe^(-λx)
   - Mean = 1/λ, Variance = 1/λ²

2. **Scale parameter β = 1/λ**: f(x) = (1/β)e^(-x/β)
   - Mean = β, Variance = β²

## Example Problems

### Example 1: Customer Service
**Problem**: Customers arrive at a service center at an average rate of 3 per hour. What's the probability that the next customer arrives within 15 minutes?

**Solution**:
- Rate: λ = 3 customers/hour = 0.05 customers/minute
- Time: t = 15 minutes
- Find: P(X ≤ 15)

P(X ≤ 15) = F(15) = 1 - e^(-0.05 × 15)
             = 1 - e^(-0.75)
             = 1 - 0.472
             = 0.528

Answer: 52.8% probability

### Example 2: Equipment Failure
**Problem**: A machine fails on average every 200 hours. If it has been running for 150 hours without failure, what's the probability it will fail in the next 50 hours?

**Solution**:
- Rate: λ = 1/200 = 0.005 failures/hour
- Using memoryless property: P(X ≤ 50) regardless of 150 hours already passed

P(failure in next 50 hours) = P(X ≤ 50)
                             = 1 - e^(-0.005 × 50)
                             = 1 - e^(-0.25)
                             = 1 - 0.779
                             = 0.221

Answer: 22.1% probability

### Example 3: Internet Connections
**Problem**: Time between internet disconnections follows an exponential distribution with mean 120 minutes. Find the probability of no disconnection for 3 hours.

**Solution**:
- Mean = 120 minutes, so λ = 1/120 per minute
- Time = 3 hours = 180 minutes
- Find: P(X > 180)

P(X > 180) = 1 - F(180)
           = 1 - (1 - e^(-180/120))
           = e^(-1.5)
           = 0.223

Answer: 22.3% probability

## Applications
1. **Reliability Engineering**: Time until component failure
2. **Queueing Theory**: Inter-arrival times in Poisson processes
3. **Telecommunications**: Time between phone calls
4. **Physics**: Radioactive decay, time between particle emissions
5. **Finance**: Time between market events
6. **Biology**: Time between mutations or infections
7. **Computer Science**: Time between system failures

## Relationship to Other Distributions
1. **Poisson**: If events follow Poisson(λ), inter-arrival times follow Exponential(λ)
2. **Gamma**: Exponential(λ) is Gamma(1, λ)
3. **Weibull**: Exponential(λ) is Weibull(1, 1/λ)
4. **Geometric**: Discrete analog of exponential
5. **Chi-square**: If X ~ Exponential(λ), then 2λX ~ χ²(2)

## Survival Function
The survival function (reliability function) gives the probability of surviving beyond time t:

**S(t) = P(X > t) = e^(-λt)**

## Hazard Function
The hazard rate (failure rate) is constant for exponential distribution:

**h(t) = f(t)/S(t) = λe^(-λt)/e^(-λt) = λ**

This constant hazard rate is a key characteristic of the exponential distribution.

## Percentiles
For the pth percentile of Exponential(λ):

**xₚ = F^(-1)(p) = -ln(1-p)/λ**

Common percentiles:
- 25th percentile: -ln(0.75)/λ ≈ 0.288/λ
- 50th percentile (median): ln(2)/λ ≈ 0.693/λ
- 75th percentile: -ln(0.25)/λ ≈ 1.386/λ
- 90th percentile: -ln(0.10)/λ ≈ 2.303/λ

## Maximum Likelihood Estimation
For a sample x₁, x₂, ..., xₙ from Exponential(λ):

**λ̂ = n/Σxᵢ = 1/x̄**

The MLE of λ is the reciprocal of the sample mean.

## Confidence Intervals
For λ with confidence level (1-α):

**(χ²α/2,2n/(2nx̄), χ²₁-α/2,2n/(2nx̄))**

where χ²α,df is the α-quantile of chi-square distribution with df degrees of freedom.

## Tests for Exponentiality
1. **Kolmogorov-Smirnov test**: Compare empirical CDF to theoretical
2. **Anderson-Darling test**: Weighted goodness-of-fit test
3. **Q-Q plot**: Plot quantiles against theoretical quantiles
4. **Mean vs. Standard deviation**: Should be equal for exponential
5. **Coefficient of variation**: Should equal 1

## Truncated Exponential
For exponential distribution truncated at time T:

**f(x|x ≤ T) = λe^(-λx)/(1 - e^(-λT)) for 0 ≤ x ≤ T**

## Shifted Exponential
For exponential distribution shifted by threshold θ:

**f(x) = λe^(-λ(x-θ)) for x ≥ θ**

Mean = θ + 1/λ, Variance = 1/λ²

## Key Formulas Summary
- **PDF**: f(x) = λe^(-λx) for x ≥ 0
- **CDF**: F(x) = 1 - e^(-λx) for x ≥ 0
- **Mean**: 1/λ
- **Variance**: 1/λ²
- **Standard Deviation**: 1/λ
- **MGF**: M(t) = λ/(λ - t) for t < λ
- **Median**: ln(2)/λ
- **Mode**: 0
- **Skewness**: 2
- **Kurtosis**: 9
- **Memoryless Property**: P(X > s+t | X > s) = P(X > t)
- **Survival Function**: S(t) = e^(-λt)
- **Hazard Rate**: h(t) = λ (constant)

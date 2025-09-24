# Markov Chains

A Markov chain is a stochastic process where the probability of future states depends only on the current state, not on the sequence of events that led to it.

## Properties
- **Memoryless Property**: P(X_{n+1} = j | X_n = i, X_{n-1}, ..., X_0) = P(X_{n+1} = j | X_n = i)
- **Transition Matrix**: P_{ij} = P(X_{n+1} = j | X_n = i)
- **State Space**: Set of all possible states

## Types
- **Discrete-time Markov Chain**: States change at discrete time steps
- **Continuous-time Markov Chain**: States can change at any time

## Key Concepts
- **Stationary Distribution**: π such that π = πP
- **Irreducibility**: All states communicate with each other
- **Aperiodicity**: gcd of return times to any state is 1
- **Ergodicity**: Irreducible + aperiodic + finite state space

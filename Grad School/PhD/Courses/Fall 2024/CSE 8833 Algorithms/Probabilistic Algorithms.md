## Deterministic vs. Probabilistic
- deterministic will always produce a given output for a given input
- probabilistic will contain steps that make random choices by using a pseudorandom number generator


## Types
- randomizations of deterministic algorithms
- Monte Carlo
- Las Vegas
- Numerical probabilistic algorithms

### Randomization
- steps that were made in a deterministic are instead done in a random fashion
- designed to break link between a particular input and worst-case behavior
- homogenize the expected behavior of inputs

### Breakdown
- use pseudorandom number generators
- $\textit{J}(I)$ = number of basic operations by the deterministic algorithm
- $\textit{J}(I)_{exp}$ = number of expected operations by probabilistic algorithm
- $B_{exp}(n) = min\{J_{exp}(I)| I \in J_n\}$ 
- $W_{exp}(n) = max\{J_{exp}(I)| I \in J_n\}$  
- $A_{exp}(n) = E(J_{exp})$ 

### Characteristics
- not usually better, and often times a bit worse than a deterministic version of the same algorithm due to the overhead of the number of calls
- Monte Carlo produce solutions very quickly and guarantee correctness with high probability
- Las Vegas never output incorrect, but have some possibility of failing to produce a solution
- Practically, obtaining solutions w.h.p is good enough!
- Choices from a set of elements
- Performance depends both on input, but also on results of randomized choice
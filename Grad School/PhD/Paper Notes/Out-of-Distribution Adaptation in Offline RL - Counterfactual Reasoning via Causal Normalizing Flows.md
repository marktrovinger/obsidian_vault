
# Things to look up
- diffeomorphic transformations


# Paper sections
## Causal RL
- causal inference + RL
- we assume a causal graph as a prior, but we can learn one if it isn't present
## Normalizing Flow
- generative model, similar to VAEs and GANs
- models are "invertible", data can pass both directions through the model, unlike most NN archs
- autoregressive is a natural structure for NFs
## Causal Normalizing Flow for Dynamic Modeling
- NFs are underutilized in world modeling
- two tuple types: true (which is what I am familiar with) and perturbed:
	- $\widetilde x = (s, a, s, ∅)$ 
	- the perturbed is the same state, and the reward set to 0
	- goal is to align the distributions of the true tuple and the perturbed, which optimizes the mapping function which in turn improves predictions
- mapping function $F_{CNF}()$ and $G()$, of which $G()$ is an MLP, transforms the perturbed tuple into the    


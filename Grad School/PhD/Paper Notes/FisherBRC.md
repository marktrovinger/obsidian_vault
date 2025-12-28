- Paper: https://arxiv.org/abs/2103.08050 
- Code: https://github.com/google-research/google-research/tree/master/fisher_brc
# Main Idea
- Problem: In actor-critic offline RL, the actor tends to be regularized in some way, but the critic isn't which leads to the critic extrapolating wildly about the value of actions that aren't in the dataset, which in turn skews the actor itself
- Approach: parameterizing the critic values as the logits of the behavior policy + an offset term, in this case using the [[Fisher divergence]], interpreting the critic values as the energy function of a [[Boltzmann distribution]]
- Experiment env: Toy Continuous Bandit, MuJoCo
- Results: Matches or exceeds SOTA when the paper was written, on the [[Offline RL Benchmark]]
Link: http://arxiv.org/abs/1706.02275

## Abstract
- As the number of agents grows, the environment continues to change, this is difficult for $Q$-learning to handle
- Adapt actor-critic methods that take into account the actions of other agents and is able to learn policies that require cooperation from other agents
- Demonstrates a training regimen for multiple agents using an ensemble of policies that makes the policies more robust


## Methods
### Multi-Agent Actor Critic
- centralized training, decentralized execution
- critic has info about the policies of the other agents
- centralized action-value function: $Q_{i}^{\pi}(\textbf{x}, a_1, \dots, a_n)$, takes inputs from the agents and outputs the $Q$ value for agent $i$ 
- if we know the actions taken by all agents, the env is stationary even as policies change

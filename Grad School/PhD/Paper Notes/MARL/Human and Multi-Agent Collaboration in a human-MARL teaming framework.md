Link: https://arxiv.org/abs/2006.07301

## Abstract
- Open source framework, COGMENT
- Real time env, unmanned AV driven by RL agents, but working with a human

## Related and Background
### TODO: read these papers
- [[Learning to communicate with deep multi-agent reinforcement learning.]](https://arxiv.org/abs/1605.06676)
- [[Counterfactual multi-agent policy gradients.]](https://arxiv.org/abs/1705.08926)
- [[Multi-agent actor-critic for mixed cooperative-competitive environments.]](https://arxiv.org/abs/1706.02275)

## Methods
### COGMENT
- agents
	- human or agent, send actions, feedback and/or recommendations to other actors
	- gRPC
- user clients
	- RL and/or heuristic agents, communicate through gRPC, can live in docker containers
- orchestrator
	- system nexus, manages system communications, reward combinations
### Hybrid MARL
TODO: read this section carefully
- D3-MADDPG
	- modifies the network of [[MADDPG]]
	- replaces Q-learning with Double Dueling Deep Q learning
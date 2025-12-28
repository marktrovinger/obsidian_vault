- Horizon scaling <-> MTRL?
- Scaling critic > scaling actor

### Environment
- Meta-World https://meta-world.github.io/
- Unified observation and action space, single robot and workspace
	- ALE has too many different visual observation spaces
		- Pong vs. Space Invaders vs. Montezuma's Revenge
		- Makes intuitive sense; easier to learn a task that is "close" in space than one that is very far
	- DOOM has a more unified visual "language" than something like ALE
		- Action space differences

### Existing 
- Multi-task multi-head SAC https://proceedings.mlr.press/v100/yu20a.html
- Soft-Modularization https://proceedings.neurips.cc/paper/2020/hash/32cfdce9631d8c7906e8e9d6e68b514b-Abstract.html
- Mixture Of ORthogonal Experts https://openreview.net/forum?id=aZH1dM3GOX

### Questions and Experiments
- Why do RL algos lose plasticity?
- Scaling parameters
	- Is scaling the reason for recent success?
	- Can we predict if a scaling method will be successful?
	- Where is the scaling most impactful?
	- How does scaling affect plasticity? Does this change with the number of tasks?
- MT 10 and MT 50
- Success rate for parameter scaling, dormant neurons for plasticity

### Results
- Scaling the critic increases performance
- Increasing both improves performance
- Increasing the number of tasks improves plasticity, increasing both works better than either in isolation

### Drawbacks
- Short time horizon
- Dense rewards
- No occlusions
- Tasks are very similar

### My Thoughts
- Baseline Architecture Results
	- Match existing implementations
- Makes sense why it won an award for scientific understanding!
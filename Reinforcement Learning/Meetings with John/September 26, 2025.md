From written notes in my notebook.
## Premeeting Notes
### Horizon Reduction Paper
#### Single Agent
-  RL algos don't scale as task complexity increases, even with more data and more compute
- Robotics tasks seem to be more susceptible to these problems, multi-step tasks are a big problem, `cube_octuple` is the most challenging task
- Problem with off-policy algos in particular
- Possible solutions the authors investigated:
	- Are the envs even solvable?
	- Are larger models the solution?
	- Are hyperparameters or design choice responsible?
##### On-Policy (PPO, GRPO)
- Problem with envs where fresh data is difficult/expensive to obtain

#### MARL
- SMACv2 has more complex scenarios
- $Q$-error would likely to be seen in more complext envs, $TD$-error would also be a problem
- Since most of the most performant algos in MARL are on-policy, we may not see the same issues in MARL settings

## Meeting Notes 
### From John
- Dataset size was mentioned
- Shortest path algos
- $n$-step returns in Sutton and Barto
### Next meeting(s)
- Looking at RLC 2025 papers
	- https://arxiv.org/abs/2503.05126
	- My assignment for the next meeting
		- 15 min. presentation
		- LaTeX Beamer presentation
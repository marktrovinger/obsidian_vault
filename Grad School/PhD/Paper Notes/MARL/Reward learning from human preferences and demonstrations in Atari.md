Link: https://arxiv.org/abs/1811.06521
Extension of: https://arxiv.org/abs/1706.03741 

# Code (pointmass.ipynb)
- Comes from DRL from human pref paper
- Collects rollouts of differing quality levels
	- Subopt, expert, rand
	- Computes metrics on those rollouts
	- Creates an augmented rollout dataset
		- Combination of the three types
		- Saves pickled versions of each
- Creates a VAE model
	- Trains the VAE on the augmented observation data
- Creates an AbsorptionModel
- Creates a DynamicsModel
	- Trains the DynamicsModel
- Creates the RewardModel
	- Trains the reward model
- Creates the Trajectory Optimizer

## General notes for code
- Uses older versions of packages, couldn't use GPU, so reduced training to make it work on my system

# Paper
## Demonstrations
- Trajectories of human behavior
	- Behavior cloning, imitation
	- BC was one of the benchmarks in the DT, makes sense; if your method isn't able to perform better, it might not be a good method
## Preferences
- Human compares pairwise short traj segments and picks those which are closer to the goal

## General Paper Notes (and literature)
- Atari disappears from the lit after 2020
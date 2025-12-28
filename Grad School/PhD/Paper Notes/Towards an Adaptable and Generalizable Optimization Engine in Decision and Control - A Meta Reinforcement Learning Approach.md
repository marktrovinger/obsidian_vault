# Overview
- we want to be able to have an optimizer be able to generalize and adapt to non-stationary environments
- based on meta-RL
- few-shot learning
- can be used on unseen tasks

# Problem Formulation
- use an RL algorithm, policy gradient, to update the policy parameters of the controller
- once the policy parameters are updated, the parameters of the RL algorithm can be updated as well
- algorithm:
	```
	while not done:
		sample task batch T_i
		for each T_i:
			Sample K trajectories from controller
			for each controller m_i:
				Execute m_i and collect data
			end for
		compute gradients for task batch, T_i
		update parameters using the parameter update eqn. 3
		sample trajectories using the new parameters
	end for
	update meta optimizer
	``` 

# Results
- better than regular RL apparently, very few experiments
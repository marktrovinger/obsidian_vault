These are a collection of notes about adding an RL library to IsaacLab that doesn't have one. I'm going to work on this for the stack task, although I am wondering if the reason it doesn't have any is that the task may not be solvable.

## Missing Files
I'm comparing the `stack` task to `reach`, as it already has working library implementations. Within the `mdp` folder, there is a `rewards.py` file that is missing from the same folder in `stack`. There are also missing files related to the libraries themselves, in the `agents` folder.

## First Steps
Based on the missing files, the first step would likely be to create a `rewards.py` file, and populate it accordingly. `reach` has three functions that dictate the reward structure (I'm copying the doc string for each one):
- `position_command_error`: Penalize tracking of the position error using L2-norm. The function computes the position error between the desired position (from the command) and the current position of the asset's body (in world frame). The position error is computed as the L2-norm of the difference between the desired and current positions.
- `position_command_error_tanh`:  Reward tracking of the position using the tanh kernel. The function computes the position error between the desired position (from the command) and the current position of the asset's body (in world frame) and maps it with a tanh kernel.
- `orientation_command_error`: Penalize tracking orientation error using shortest path. The function computes the orientation error between the desired orientation (from the command) and the current orientation of the asset's body (in world frame). The orientation error is computed as the shortest path between the desired and current orientations.
The two command position functions seem interchangeable, I will need to look into the reason why there are two functions that seem to perform the same function.

The structure of the rewards for this task may already be laid out (if somewhat different) in the stack task in [Panda-Gym](https://panda-gym.readthedocs.io/en/latest/index.html). The `stack` task in IsaacLab has 3 cubes, but the idea should be the same. 

### Action Items
- ~~Research the structure of the rewards in Panda and see if they can be mapped onto the task in IsaacLab~~
	- Add notes to this result, ideally tomorrow
	- Results: Probably not easily; the way that rewards are structured in Lab make it more difficult to "port" over the reward function
- ~~Read the `reach_env_cfg.py` file and note differences between it and the `stack_env_cfg.py` file, likely need to add support for the rewards there as well, along with how the `rewards.py` module is referenced.~~
	- Add notes here, also tomorrow during the research block
		- There will need to be functionality for rewards as predicted
- The `Isaac-Lift-Cube-Franka-v0` might be a better starting point; the task involves moving a cube to a specified location, training a policy now, planning to run the `play` script as well
	- Add notes here, during research block tomorrow
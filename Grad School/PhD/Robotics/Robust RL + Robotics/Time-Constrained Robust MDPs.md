
### 

### Questions from Dr. Chen
- Do the authors vary the parameters mentioned in Table 7 over time in the same episode or across different episodes?
	- It looks like they change the parameters over 1000 steps, looking into the code
		- `scheduler.py` contains the linear, exponential, and logarithmic scheduling for perturbing the observations
		- `step()` function in `tc_mdp.py` *looks* like it is where the actual perturbation happens, for training at least, while the eval perturbation happens according to the scheduler?
		- `_computes_new_params()` takes the action from the adversary and clips the action based on the `action_dict`?
		- $\psi$ are the perturbed parameters and the observation is `(obs, adv_obs)`
		- the perturbations occur every timestep, in the `step()` function 

### Questions for Dr. Chen
- Would replication of this paper be a worthwhile project? 
	- Since I already have the code, and they don't have scripts for reproduction, maybe using the codebase to replicate plots?
- Specific type of non-stationarity to target and model/eval
	- The types of non-stationarity in the paper are parameters in the environment that would make it difficult to operate the robot in the env
	- Would targeting non-stationarity around the joint dynamics of an arm be a logical direction to take the work?
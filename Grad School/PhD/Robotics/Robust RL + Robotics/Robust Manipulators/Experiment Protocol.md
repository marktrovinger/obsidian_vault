From [Robust Gym] which I think references a different paper.

### In-Training 
- The disruptor module affects the agent and the environment in both the training and testing stages.
### Post Training
- Disruptor module only affects the agent and environment during the testing stage.

## Evalution for Standard RL
According to the plots, there are three levels of disruption for PPO, for example:
- Just PPO
- PPO-S-0.1
- PPO-S-0.15
Here the $S-0.1$, refers to disrupting the state with a mean of 0 and a standard deviation of 0.1. Action attacks follow a similar pattern. Agents are trained for 3M timesteps.

## PPO Hyperparameters
- buffer size 4096
- lr 3e-4
- epoch 100
- steps per collect 2048
- batch size 64
- testing num 10
- vf coef 0.25
- gae lambda 0.95
- lr decay True
- eps clip 0.2
- value clip 0
- recompute adv 0
- hidden size \[64, 64\]
- gamma 0.99
- steps per epoch 30000
- repeat per collect 10
- training num 8
- rew norm True
- ent coef 0.0
- bound action clip clip
- max grad norm 0.5
- dual clip None
- norm adv 0

## Approach to using algorithms
### PPO
Given that the action provided to the environment differs from the Gym standard, there are a couple of approaches that might work.
 - Use CleanRL's PPO implementation, but alter the step to use the disruption module
	 - CleanRL uses several wrappers in the `make_env()` function, should we be using those as well?
 - Investigate using [RSL-RL](https://github.com/leggedrobotics/rsl_rl) for PPO, altering the commands as needed?

## SAC
Similarly to PPO, there are a couple of choices:
- Use CleanRL's PPO implementation, but alter the step to use the disruption module
	 - CleanRL uses several wrappers in the `make_env()` function, should we be using those as well?
 - 


- ~~Dies before reaching the end of the task, could be related to current position not updating correctly
- ~~need to fix observation space and action space not returning correct values
- ~~update action space to multi-discrete

## Q-Learning updates
- ~~update definition to use the environment, look at how cleanRL or sb3 do it
- ~~need to update training loop to train
- ~~need to either reformulate actions or flatten/unflatten actions as they come in/go out

## Re-eval assumptions
- What does the achieved goal and desired goal actually tell us?
	- It gives us the information that we need about item placement, the built-in method for computing reward may be a better match than something I write
- 

## Possible Simplifications
- Start with `JengaPickandPlace` using a deterministic framework for testing, moving to more complex envs once bugs are worked out
	- Wrapper tasks:
		- Less hardcoded: currently, the wrapper has to know how many objects are in the scene, since the observation contains all of the scene information, it might be possible to iterate through and count, instead of specifying this information

## Current Bugs:
- `NoneType` return error from step
	- Hypothesis: The environment is somehow reaching either a state that can't exist or there is some issue with the way the state space of the blocks is translating to the state that the Q-learning algorithm uses
- Object positioning
	- Are the objects in the scene positioned the way they should be?
		- ~~Run the code several times with screenshots to compare positions
		- Yes and no; the block position remains the same, but the block orientation is not correct
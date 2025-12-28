- Debugged using `ViZDoom DT MWH` launch profile
- Error message: `RuntimeError: shape '[128, 60, 1, -1]' is invalid for input of size 42240`
- Bug is in `model_doom_multidisc.py`, line 35, reshaping oh
	- `one_hot_action()` method is currently hardcoded to `deadly_corridor`, needs to be changed to be more general
	- `my_way_home` action space: `(128, 60, 1, 2)` 
	- `deadly_corridor` action space: `(128, 60, 1, 4)`
- Code added:
	- First attempt at handling the lower number of actions
	- Created another debug config, `ViZDoom DT DC` for `deadly_corridor`

## First Experiment:
- On commit: `8512b9d`
- Goals:
	- Test if change works, does it generate the correct shape?
- Results:
	- Index out of bounds, should be two values, not 3

## Second Experiment
On commit: `8512b9d`
- Goals:
	- Test if change works, does it generate the correct shape?
- Results:
	- Error on action embeddings, how does `squeeze()` work?
	- Interesting wrinkle, the `one_hot_actions` variable, which should have a final dimension of 9, is 6 instead

## Questions
- Do the other non-shooting envs have similar action spaces?
	- My Way Home might be the only one with this action space

## Third Experiment
Same commit
- Goals:
	- Determine how the logits are constructed so that I can determine what range of logits need to be evaluated
		- Logits size of 7680 is larger than the target size, so I need to look at how the logits are calculated
![[Pasted image 20230828201111.png]]
- I need to make the shapes match, not sure how to do that
- `doom_utils`

## Batch Size Bug
- On final iteration, the batch size drops from 128 to 12, which causes the `one_hot_action` function to return `None`
	- Why does this happen?
	- What would be the appropriate fix to this?
	- Has Perusha encountered this type of bug?



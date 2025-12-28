## General Info
- It looks like we can execute SF experiment files from anywhere, as long we invoke the experiment files like this: 
	- `python -m sample_factory.launcher.run --run=sf_examples.vizdoom.experiments.doom_basic --backend=processes --num_gpus=1 --max_parallel=2 --pause_between=0 --experiments_per_gpu=2`
	- In our experiments the `sf_examples.vizdoom.experiments.doom_basic` would be replaced by the experiment file of our choice
- The following imports are required:
	- `from sample_factory.launcher.run_description import Experiment, ParamGrid, RunDescription`
## ParamGrid
- Appears to work similarly to `pipeline` in `sklearn`, we need to think about what values would make sense in the grid for our experiments
	- Looking at some examples, we can test the efficacy of changes like `ResNet` instead of `CNN` for image encoding, different seeds, etc.

## Experiment

## RunDescription

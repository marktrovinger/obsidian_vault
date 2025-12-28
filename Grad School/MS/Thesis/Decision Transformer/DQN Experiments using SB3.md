## Environment Setup
Create a conda env
Install PyTorch
Install VizDoom using Conda instructions
Install SB3 from GitHub

## ReplayBufferCallback
- Uses BaseCallback from SB3 to sample the environment and the model when needed, logs the interactions to a ReplayBuffer
- Writes the logged interactions when the training ends, could do this with the `_on_training_stop()` function.
- Currently not using `optimize_memory_usage`, should talk to Perusha

## Experiment Results
TL;DR - Pretty bad, even with basic environment
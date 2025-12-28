# Analysis Notes
Created: 2023-01-20 21:12
* `run_dt_atari.py` is the entry point, creates the `GPTConfig`, `GPT`, `TrainerConf`, and `Trainer` objects, and loads the replay data, using `dopamine.replay_memory.circular_replay_buffer`, the trajectory representation *might* be computed here, but I need to investigate this further
* 350k timesteps and a batch size of 128 will work on local workstation, but eval return is less than target, look into using 2060 for daily tasks and 3080Ti only for training, each epoch takes about 7.5 minutes at 300k timesteps + eval time (roughly 2 minutes)
* Training on less than 500k timesteps yields a model that will not perform as well as one trained on the full dataset, best eval was 15(?), with the full dataset getting the expected 20
* Lambda Labs' A10 instance should be sufficient for full testing, 300 GB of RAM and 24 GB of VRAM
* W&B integration sort of works, need to figure out if it needs to be in `trainer_atari.py` or add a callback with variables
* nanoGPT might be a suitable replacement for minGPT, depending on what changes are needed to add the infrastructure for DT and dataset loading
* Model configuration is handled by the `GPTConfig` class, and is created by the `GPT` class, training is handled by the `TrainerConfig` and `Trainer` classes
* The raw data is massaged into the right form by the `StateActionReturnDataset` class, which puts it into a form needed by the transformer
* The `state_encoder` looks very similar to the preprocessing done in the Nature paper for DQN, ask Perusha what she thinks
* Format for data for next week, make sure VizDoom can generate some data before next week, start with SB3 to generate data, look at Dopamine
* Add Perusha Moodley as collaborator to GitHub project
 
## References
1. https://github.com/google/dopamine
2. 
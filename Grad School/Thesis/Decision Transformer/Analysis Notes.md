# Analysis Notes
Created: 2023-01-20 21:12
* `run_dt_atari.py` is the entry point, creates the `GPTConfig`, `GPT`, `TrainerConf`, and `Trainer` objects, and loads the replay data, using `dopamine.replay_memory.circular_replay_buffer`
* 350k timesteps and a batch size of 128 will work on local workstation, but eval return is less than target, look into using 2060 for daily tasks and 3080Ti only for training, each epoch takes about 7.5 minutes at 300k timesteps + eval time (roughly 2 minutes)
* Lambda Labs' A10 instance should be sufficient for full testing, 300 GB of RAM and 24 GB of VRAM
* W&B integration sort of works, need to figure out if it needs to be in `trainer_atari.py` or add a callback with variables
 
## References
1. https://github.com/google/dopamine
2. 
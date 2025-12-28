### General
- 2023 paper
- Code: https://github.com/UCL-IFT/noisyenv
### Contributions
- Novel noisy wrappers
- Noise rate as a parameter
- Evaluation wrappers on Mujoco tasks

### Limitations
- Selection of noise types and noise rates not explored
- Not consistent in improvements, optimal selection of noise/noise rate is non-obvious
- Automation of noise selection (possibly similar to learning rate annealing?)
- Combination of different noises types was not explored (possible?)

### Previous Work
- Action space noise is well-studied
- Transition dynamics noise is a novel approach as of the paper
	- Random Early Termination

### Next steps:
- [[PPO]] benefits from reward scaling in these environments, has this been studied in other work? Does this hold for other continuous control tasks?
- [[ROBUST GYMNASIUM - A UNIFIED MODULAR BENCHMARK FOR ROBUST REINFORCEMENT LEARNING]] may be useful, both more broadly and in investigating PPO and reward scaling
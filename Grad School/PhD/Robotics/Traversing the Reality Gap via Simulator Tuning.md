- 2020 paper
- Collins, [[Benchmarking Simulated Robotic Manipulation Through a Real World Dataset]] and [[Quantifying the Reality Gap in Robotic Manipulation Tasks]]
- Similar to existing work, physics engines are good at different things

### Existing Approaches
- Data driven (real world data)
- Robust controllers (noise or random simulation parameters)
- Hybrid (large numbers of unrealistic scenarios)

### Paper's Approach
- Simulator parameters as an optimization problem, used SciPy's optimise package

### Results
- Default simulator timestep, as this was set by the creator of the simulator and likely the best option
- Get accurate friction values
- Get accurate max joint velocity for actuators
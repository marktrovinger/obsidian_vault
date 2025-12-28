- Paper Link: https://pure.tue.nl/ws/portalfiles/portal/303136640/Deep_Reinforcement_Learning_for_Real-Time_Assembly_Planning_in_Robot-Based_Prefabricated_Construction.pdf
- Code: https://github.com/hyintell/drl-assembly-planning

# Contributions
- Created a simulator env for using DRL in a construction setting
- Proposal of planning methods using DRL
- Benchmarks for assembly planning using DRL

# Environment Setup and Dynamics
Reward structure: 
$$
R_{c_i,t} = 
\begin{cases}
t \cdot \frac{r_0}{c_i} + i \cdot c_i, t\leq \epsilon \\
\epsilon \cdot \frac{r_0}{c_i} + 2 \cdot (t - \epsilon) \cdot \frac{r_0}{c_i} + i \cdot c_i, t > \epsilon \\
\end{cases}
$$

Where $i$ is a single component, and $c_i$ represents the serial number of the component and $t$ is the timestep of the component, and $\epsilon$ is the step threshold
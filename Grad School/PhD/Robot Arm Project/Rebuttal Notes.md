# Reviewer 1:
The paper made several assumptions and restrictions, especially the grasp pose estimation. The authors should have a plan to overcome these restrictions.
- How much do I need to do for this step?

Even though the authors discussed the reward function in section 3.4, it is still not clear how the rewards are defined. Please include more clear definitions or equations to explain the reward.
- The definition of the reward is still somewhat fuzzy, we had discussed using the component numbering in the reward function, similar to Zhu et al, do we want to revisit that?

The abstract has too much background information and too little methodology.
- How much should I do here?

# Reviewer 2:
Additionally, the reinforcement learning approach benefits from inverse kinematics to simplify action space, but it is unclear how well this generalizes to more complex, constraine workspaces where inverse kinematics may not always provide an optimal or feasible solution. Addressing this in the discussion or limitations section would provide a more complete perspective on the method's applicability.
- We do probably need to think about this longer term

Additionally, while the paper presents quantitative comparisons with other RL approaches, the discussion on hyperparameter tuning and sensitivity is somewhat limited. Since RL methods can be highly sensitive to hyperparameters, a brief discussion on how these were selected and whether small changes significantly impact performance would be helpful.
- The hyperparameters discussed might refer to the non-deterministic algos; very little tuning was done for those on this task, should I work on doing a limited set of tuning for these, along with the Q-learning hyperparameters?

# Reviewer 3:
Provide further details on the reward structure used during training, including potential trade-offs in balancing sparse and dense rewards.
- Currently, we are not using dense rewards at all for the non-deterministic algorithms, should we consider doing so?

Address the challenges of scaling the framework to full-scale construction tasks and how issues such as dynamic environmental changes and sensor noise would be managed.
- Similar to the other reviews
### Action Items
- Better understanding of KL divergence and the algos that use it as a regularizer, such as PPO
- Robust Sarsa and Max Action Difference methods don't really make much sense to me, I need to look at how the code works for this paper
### Analysis (Nov. 11)
- Lays out the theoretical underpinnings of the state adversarial MDP and how existing algorithms can extended
- Idea
	- $v(s)$ is the adversary so, $\pi(a | v(s))$ 
	- doesn't "replace" the state the agent is in; the only the perception (?) of the state the agent is in, so the agent will transition from $s$ to $s'$
	- leads to suboptimal actions, as the agents takes actions in $v(s)$ but receives the reward of $s$
	- deterministic, $v(s) \in B(s)$, task specific neighboring states (this would be closer to sensor noise an a true attack, as the attack would be neither deterministic, nor a neighboring state)
	- meaningful, but not accurate
	- goal is to minimize the total expected reward for a fixed $\pi$
	- [ ] the strongest adversary under the optimal policy: $v^*(\pi)$ 

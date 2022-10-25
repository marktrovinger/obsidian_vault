# Policy Gradients
Created: 2022-10-24 12:51

Policy gradients are fundamentally different from algorithms that use a value function, as they try to optimize the policy more directly. Examples of value based methods would be SARSA, DQN and Q-Learning more generally. These types of algorithms are referred to as *policy-based* functions. These form a continuum with value based algorithms, with actor-critic algorithms being the intersection of that Venn diagram. In such algorithms, we are trying to increase the performance of a parameterized policy, in this case using gradient ascent (the book refers to this as regular gradient descent on the negative performance). The math for this looks like this: $J_i \theta_i = \mathbb{E}_{s_0 \sim p_0}[v_{\pi_{\theta_i}}(s_0)]$ 

The first algorithm in this family is known as the REINFORCE algorithm. 

## References
1. Grokking Deep Reinforcement Learning
2. REINFORCE Paper
3. A3C Paper
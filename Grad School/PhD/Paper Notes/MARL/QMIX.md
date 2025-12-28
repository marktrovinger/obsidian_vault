## Questions 
#### What issue or gap does the paper address?
- Decentralized policies
	- Helps the problem of partial observability, where the agents have incomplete information, so that each agent needs to only examine their local obs history
	- The way that action-value functions work makes this more difficult; centralizing the action-value function $Q_{tot}$, makes that function difficult to learn and doesn't offer a way to extract the decentralized policy, so that a given agent has a way to select a specific action for a specific observation
	- IQL's approach is to basically ignore the problem and let each agent learn their own action-value function, but this has drawbacks; lack of convergence and offers no mechanism for representing agent interactions
	- Fully centralize the action-value function is the approach by COMA, needs on-policy which isn't sample efficient
	- VDN tries to split the baby, summing $Q_{tot}$, allowing agents to take greedy actions with respect to its own $Q_a$. Ignores extra state info and limits complexity.
	- Similar approach to VDN, but it isn't necessary that full factorization is used, just a global `argmax`, but monotonicity must be use

#### How was the research conducted? What framework or design was used?
- Network Arch
	- Mixing Network
		- Takes the $Q_n$ output from the agent network, along with the input weights from the hypernetwork, mixing them monotonically, enforcing this constraint by restricting the weights (not biases) of the network to non-negative values
	- Hypernetwork
		- Generates a single layer's weights for the mixing network, taking the state $s$ as input, reshapes the output as necessary
	- Agent Networks
		- DRQN, take the individual agent observation and the last action as input, outputs the $Q_n$ value for that agent
- StarCraft 2
	- Ablation Experiments
		- QMIX-NS, without the hypernetworks
		- QMIX-Lin, weighted sum of the $Q_a$ values instead of the non-linear mixing method used in the full algorithm
		- VDN-S, adds a state-dependent term to the sum of the $Q_a$ values.

#### What are the main results or takeaways?
QMIX outperforms both IQL and VDN in all tasks, with test win rate as the metric. The heuristic approach is noted as a dashed line, with QMIX able to either match or exceed the performance of the heuristic approach.

The ablation experiments demonstrate the value of the full QMIX method, with the ablated versions unable to match the performance of QMIX, with the exception of the 3m scenario, which is the easiest scenario in the setting.

#### Any strengths? What’s effective or well-done in this paper?
The validity of the approach is clearly demonstrated, indicating that this work represents a state of the art approach.

#### Any weaknesses, limitations, assumptions, or critiques?
While the focus on SC2 makes sense, given the state of MARL environments, the SMAC environment takes primarily visual data as input, and the authors do not indicate how valid the approach would be if applied to a continuous control problem, such as robotics.

#### How does this connect to your research interests or projects?
QMIX is a standard algorithm for comparison when developing new algorithms. The mixing approach is used in the proposed robust MARL approach Dr. Sun and I are working on.

## Wrap Up
Great paper! Really learned a lot from going through the paper, and how the approach might influence future works.
### Next Paper Ideas
- SMACv2
- MADDPG paper
- MAPPO
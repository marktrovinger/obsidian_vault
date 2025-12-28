- Paper: https://arxiv.org/abs/1812.02900
- Code: https://github.com/sfujim/BCQ

# Main Idea
- generate plausible candidate actions that have a high degree of similarity to a batch
	- also penalize rarely or unseen states, using a modified form of [[Clipped Double Q-Learning]] 
- four parameterized networks
	- generative model: $G_{\omega}(s)$
	- perturbation model: $\xi_{\phi}(s, a)$ 
	- two $Q$-networks: $Q_{\theta_{1}}(s, a)$, $Q_{\theta_{2}}(s, a)$ 
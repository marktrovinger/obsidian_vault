- Paper: https://arxiv.org/abs/2106.06860
- Code: https://github.com/sfujim/TD3_BC

# Main Idea
- regularize the policy update step of the [[TD3]] algorithm:
	- $\pi = \text{argmax}_{\pi} \mathbb{E}_{(s,a)\backsim D}[Q(s,\pi(s))]$ 
	- to:
	- $\pi = \text{argmax}_{\pi} \mathbb{E}_{(s,a)\backsim D}[\lambda Q(s,\pi(s)) - (\pi(s) - a)^2]$ 
	- $\lambda$ is how the strength of the regularizer is controlled
- normalize the dataset's states, so they have a mean of 0 and standard deviation of 1 improves the stability

# Results
- performs better than most existing algorithms, with comparable performance to [[FisherBRC]] while less computationally expensive and much simpler to implement
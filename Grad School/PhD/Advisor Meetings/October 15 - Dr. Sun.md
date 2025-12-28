## Papers of Interest
- http://arxiv.org/abs/2406.07541
- https://arxiv.org/abs/1812.10687
- https://arxiv.org/abs/1812.02900
- https://arxiv.org/abs/1906.00949

## DT as de-noiser idea
- TODO:
	- Investigate potential existing work that has a similar underlying hypothesis
	- Interrogate the underlying hypothesis for soundness
	- Writeup in a LaTeX document the idea, and look for holes in the approach
- Questions:
	- Would this approach actually de-noise or just change the underlying transition dynamics?
	- What % to perturb the dataset to test the efficacy of this approach? Also, perturb the states or the states and actions?

## Underlying assumptions in offline RL
- OOD problem
	- How to address when states are very outside OOD?


## Diffusion
- Diffusion tries to recover the original state
- Diffusion based de-noising
- Gaussian noise is most common


## Dr. Chen
- Work on his project first, design a reward structure
- Talk to him about integrating the two projects

## Follow-up
- Email from Dr. Sun:
	- Minimize a gradient for $f(x)$ with a gradient: $\nabla f(x)$ 
	- State: $(x, \nabla f(x))$ 
	- Action: $\delta x$ 
	- Reward: $-f(x) - \|\nabla f(x) \|$ 
	- Next state: $(x + \delta x, \nabla f(x + \delta x))$ 
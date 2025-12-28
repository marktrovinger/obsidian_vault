Link: http://arxiv.org/abs/2406.00244

## Need to Read
ReAct Paper: https://arxiv.org/abs/2210.03629 [[ReAct Paper]]
LLMs in Bandits: https://arxiv.org/abs/2403.15371, https://arxiv.org/abs/2403.16843
Steering LLaMa 2: https://arxiv.org/abs/2312.06681

## Reproducing Notes
Mixtral 8x7B: https://huggingface.co/mistralai/Mixtral-8x7B-v0.1

# Basic Takeaway
LLMs tend to be overconfident in decision making tasks, and require a mechanism to keep them exploring the action space instead of exploiting.

# Overview
## Steering Vector
- dataset of logged interactions LLM <-> environment
- what is it?
	- entropy weighted average of the representations that an LLM produces right before the decision is made
	- applied at decision time to a specific layer to the representation corresponding to the tokens generated
- Open questions
	- What does this steering vector look like? 
		- I think this is the encoded representation of the token, that is present in all NLP models

## Uncertainty over actions/ Token and Action Generation
### Setup
- 2 armed bandits, with means $\mu_0, \mu_1$ and variances $\sigma_0=10, \sigma_1=10$
	- TODO: look more into bandits, make sure I understand everything about them
- Method:
	- generate 25 completions, using a prompt that the agent should evaluate options to maximize reward over time
	- as the entropy decreases, the effect that the generated tokens have on the final decision basically goes to zero
	- why do an intervention on the token-generation step instead of the action generation?
		- TODO

# EAST
## Steps
1. Compute the steering vector 
2. Modify the agent behavior using the generated steering vector

## Steering Vector (detailed)
1. We need to compute activations, $z_t^k = f^\ell(P_t^k)$, where $P$ is the prompt and extract the representation corresponding to the last taken in prompt
2. Estimate the entropy $h_t^k = - \Sigma_{a\in A}\pi(a|P_t^k)log(\pi(a|P_t^k))$ of the action distribution, by extracting the action from $M$ completions and computing entropy of those actions, but only if they are successful
3. Compute the steering vector, $u = \frac{1}{Z} \Sigma_{k=1}^K \Sigma_{t=1}^T h_t^k (z_t^k - \frac{1}{T} \Sigma_{t'=1}^K z_{t'}^k)$ 

## EAST
- add the steering vector, at each step, to the representation at layer $\ell$ at the position of the last token
- the steered representation: $\hat{z_i} = z_i + \beta u$, where $\beta$ is a multiplier for the amount of steering

# Experiments
## Thoughts
- The response from the model indicates a greater degree of exploration when using the EAST method
- Increased entropy in the actions
- Top words w/EAST vs. w/o EAST are very different 
- Adding the steering vector to the middle layers (16) has the greatest effect on the entropy
- EAST generalizes across prompts and steering vectors transfer across prompt settings
- EAST creates a representation about the uncertainty in decision making
- the steering vector has a positive impact on decision-making, this is distinct from simply adding a perturbation to the LLM's forward pass

## Discussion
- only works with discrete actions
- doesn't affect how much exploration should occur (compared to the observation space), nor how the behavior should change over time
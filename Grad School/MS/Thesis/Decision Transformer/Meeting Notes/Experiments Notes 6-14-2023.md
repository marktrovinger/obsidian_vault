Link: https://docs.google.com/document/d/1QNdYkY3jKZa_efzaB2D--qbcV27rwdeJ8n7nQyJvRYg/edit

Overall:
- For initial paper, do we want to test with the six basic scenarios, without taking into account things like the multi-discrete action space of deadly corridor? This can be discussed in a future work section.
- Do we want to use this as a foundation for more work in interpretability? The interpretability work has used very basic environments (GridWorld, etc), and would the more complex scenarios in Doom give rise to more complex behavior in the transformer? Look at [[Understanding RL Vision]] for an idea of how we can apply that work.
- 

HGS:
- Train the agent and then run to generate data of any length
	- Discussed; we probably can't do this very easily using the existing SF infrastructure
- Keep those parameters for the other scenarios, will give us a good baseline versus tuning the h-params for each scenario. Look at training loss at the end of 5 epochs, or possibly look at early-stopping.
- NoPE
	- Look at code for how this would work, and try to understand the theoretical reasoning for why this happens, link to paper: https://arxiv.org/abs/2203.16634
- Dropout
	- Have we looked at this using 128? Not yet. I will test this.
		- Generate videos and see if bad habits are present.
	- I'm not sure what would be causing the bad habits, maybe the skip tri-gram not working correctly?
- Distillation
	- Paper: https://arxiv.org/abs/2210.14215

 Deadly Corridor:
 - Is this using the multi-discrete, or basic movement?
 - Action space
	 - Look at other scenarios that use multi-discrete
	 - Idea: embed multi-discrete using a higher-dimension convolution?
	 - Action Position embedding
		 - What is meant by extending the mode?
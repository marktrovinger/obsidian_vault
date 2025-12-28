- Paper: https://arxiv.org/abs/2006.03647
- Code: https://github.com/matsuolab/BREMEN

# Main Idea
- Improve "deployment efficiency"
	- loop of:
		- collect data from environment to put into a dataset
		- train a policy (or update a policy) with that dataset
		- deploy to environment
	- continuum of greater efficiency, for offline algorithms, to lesser efficiency in the case of online algorithms
	- useful in scenarios where deployment cost is very high, eg. robotics, healthcare
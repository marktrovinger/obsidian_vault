Link: http://arxiv.org/abs/2204.05862

## Abstract Notes
- They finetune an LLM to be helpful and harmless
- Alignment training helps with all NLP tasks
- Can also be used for more specialized tasks, such as coding in Python and text summarization
- Iterated online training mode
	- models and policies are updated weekly from HF data
- Linear relation between RL reward and square root of KL divergence between the policy and its initialization 



# Questions
- How do they define these terms (helpful and harmless)?
- Which NLP tasks were examined, and by how much did the alignment training contribute?
- Where does the HF data come from?
- Why is the linear relationship between RL reward and the square root of KL divergence important?

# TODOs:
- Investigate and update questions
- Investigate KL divergence (I know the term, but not well enough to explain it)
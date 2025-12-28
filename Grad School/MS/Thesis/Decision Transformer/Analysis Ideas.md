## Ablation Studies
### Batch Size
Currently we are using a batch size of 64, does ablating the batch size make sense in the context of Transformers?
### Rollout Length
We are using a rollout length of 128, is there some intuition for this value? Can we change the rollout length, and if so, what is the result?
## Precision
Can we use or implement some method for using fp16, or similar lower precision values? HF has that built in for "normal" Transformers (CV, NLP)
	- Investigate if we can use it for DT using HF's implementation

## Improvements for specific envs
### Multi-Discrete
- GATO uses a multi-discrete action space, how did they accomplish it?
- More rigorous analysis of My Way Home, can we pinpoint why the performance is so bad, and offer solutions?
- Can we flatten the action space in multi-discrete, similar to how my way home flattened works?
- Why doesn't my way home flattened work in some situations?
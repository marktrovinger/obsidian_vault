## General Info
- Dependent variables (like loss and accuracy) or output metrics should be saved with `wandb.log` instead. (instead of `wandb.config`)
- Use `wandb.config` for parameters such as `env`, `batch_size`, and `epochs`, other variables that should be examined are [here](https://huggingface.co/docs/transformers/model_doc/decision_transformer). Pass the config dictionary to `wandb.init()`
- In the training loop, use `wandb.log()` to log dependent variables (as a dictionary)
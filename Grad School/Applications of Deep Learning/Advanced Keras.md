# Advanced Keras
Created: 2022-10-20 11:22
## Workflows
Start easy, then get more complex, known as progressive disclosure of complexity. This means that you don't need to learn everything up front.

### Models
The Sequential API, which we have used, is on the far side of the spectrum, aimed at novice users. Sequential is basically a Python list, which limits it to simple stacks of layers, and a single input and output. The Functional API spans both standard use cases and niche uses, uses a graph-like model architecture. Functional also supports MIMO, and is the most commonly used framework. From there, subclassing is for researchers, who are writing everything from scratch. Subclassing doesn't allow you to access any of Keras's features, and any mistakes made will be your problem!

It shouldn't need to be stated, but use the right tool for the job! Functional is likely going to be the best choice for the overwhelming majority of scenarios.

### Loops (Training and Evaluation)
Depends of workflows, `fit()` on the simpler side, but you may need to write a training algorithm from scratch, or loss function, etc. You can pass callbacks to `fit()` which can schedule actions to be taken later. 

Metrics for measuring a model's performance are builtin to Keras, but you can also write your own, by subclassing `keras.metrics.Metric`. Along with that, you also need to override three functions: `update_state()`, `result()`, and `reset_state()`. 

Callbacks are a powerful tool to add functionality to the `fit()` method. One builtin callback is model checkpointing, `keras.callbacks.ModelCheckpoint`, which allows for saving models at different points. Early stopping is also implemented as a callback, `keras.callbacks.EarlyStopping`. Changing the learning rate is also implemented as a callback, and is a good idea in general. Tensorboard is also done as a callback, W&B as well. If you need to implement your own callback, you can subclass the `keras.callbacks.Callback` class. Pay attention to what functions need to be overloaded!



## References
1. 
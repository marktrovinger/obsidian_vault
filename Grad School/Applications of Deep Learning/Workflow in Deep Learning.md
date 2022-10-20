# Workflow in Deep Learning
Created: 2022-10-20 11:06

## Task Definition
The most important part of the workflow is to define the task. Time spent working on this step can save time and money further down the road. To do this we must frame the problem, collect a dataset, understand the data. Data collection is THE WORST, it requires the most time and money during development. It has lead to a saying, "data matters more than algorithms". You need to ensure that the data is representative of the production data, best done by collecting directly from the environment. The problem of concept drift is also to be taken seriously. 

## Model Development/Deployment
After dataset has been curated the model can be developed. This has been discussed in detail prior to this lecture. Once this is done, the model should be deployed, mostly as an inference model. The most common method is as a REST API, using a web library such as Flask. TensorFlow has a library for shipping models as APIs; TaskFlow Serving. 

Another method for deploying is to do edge deployment, where an edge device, such as a phone hosts the inference model. TensorFlow Lite can be used for this task. There are methods for reducing the size of the model for edge, such as weight pruning and weight quantization (use 8 instead of 64 bits). Deploying a model directly in the browser is also possible, using TensorFlow.js.

Once a model has been deployed, you need to keep track of how it is doing!

## References
1. [Unreasonable Effectiveness of Data](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/35179.pdf)
2. [Model Optimization](https://www.tensorflow.org/model_optimization)
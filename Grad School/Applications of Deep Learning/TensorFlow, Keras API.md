# TensorFlow, Keras API
Created: 2022-09-29 10:30

* Chain rule is used for backpropagation
	* `GradientTape` API in TensorFlow perfoms this for us
	* `tape.watch()` is necessary if using `tf.constant()` 
	* Nested `GradientTape` loops can compute second and higher order gradients
* Linear Classifier in TF
	* Implements the $y=Wx + b$ 
	* Classifies a point as belonging to one of two classes, basically which cloud of points does a new point belong to?
	* If our prediction is $\geq 0.5$ then class is $1$, $0$ otherwise
	* Training step computes the gradient loss wrt W and b, adjusts based on learning rate
* Keras API
	* Higher level than TF
	* Objects
		* Layers and `model`
			* Building blocks of deep learning
			* Weights contain the knowledge of the NN
			* Types for input
				* Vector uses fully connected (`Dense` )
				* Sequences use LSTM or `Conv1D`
				* Images use `Conv2D` 
				* LEGO of Deep Learning 
		* A loss function
			* Feedback signal
		* Optimizer
		* Metrics
			* How to define final performance of the model
		* Training loop
			* Mini-batch SGD
		* Automatic Shape Inference
			* Determines the shapes needed for input on the fly
		* Models
			* Graph of layers
			* Network topologies
				* Two-branch
				* Multihead networks, eg Transformers use multiple attention heads
				* Residual Connections
			* Building
				* subclass `Model`
				* `Functional` API
		* Hypothesis Space
			* The topology of a model 
			* Picking the right network is more art than science
			* Best practices and principles
			* You know how you get to Carnegie Hall, don't you?
		* Functions
			* `fit()` method 
				* `data` 
					* inputs and targets, `NumPy` array or `TensorFlow DataSet` object
				* `epochs` 
				* `batch_size` 
					* number of training samples used to compute gradients for one update step
			* `predict`
				* Makes predictions
				* Iterates over data and returns an array of prediction probabilities
		* Loss and Metrics
			* Goal is build modes that generalize well, so that it still performs well on unseen data
			* Don't memorize (mapping between training samples and labels)
			* Use a validation or holdout set
## References
1. 
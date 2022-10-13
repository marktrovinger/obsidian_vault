# Optimization and Generalization
Created: 2022-10-11 10:47

## Introduction
We adjust the model to get the best possible performance on the training data, this is the learning part of machine learning, we want to avoid underfitting in this scenario. We want our model to perform well on data it has never seen before, to avoid overfitting. There is a push-and-pull between optimization and generalization, similar to explore-exploit in RL.

In the case of underfitting the loss curves for both training and validation are both high, and when both are low is known as a robust fit, overfitting is when the loss curve for validation increases when the curve for training is low. The number of nodes in the hidden layer contributes to overfitting/underfitting, an example will be shown later.

## Overfitting
Overfitting has several causes, noisy data is one. If the dataset has features that are ambigous, this can lead to overfitting. If features are rare, and have correlations that are not what they appear to be, this can also cause overfitting.

Noise in datasets can take different forms, mislabeling will cause problems as the model will learn mappings that are incorrect. Ambigouity in features can force a model to remember datapoints instead of ignoring points that are too close to another class. Rare features and spurious correlations do not need to occur more than a few times to cause problems. The example in class is the MNIST dataset with noise added, look at the notebook for more details.

## Generalization in Deep Learning
Universal theorem, can fit any function. The structure of information in the world is more important to generalization than the models themselves. Another demo is MNIST with shuffled labels.

### Manifold Hypothesis
While the possible problem space for MNIST is huge, $256^{784}$ , the actual digits only occupy a small space comparitively. The handwritten digits form a manifold within the space of possible arrays, this is a lower-dimensional subspace of the parent space. The manifold of the MNIST digits illustrate that changing a single digit with small changes can morph that digit into a different one.

The two manifold hypothesis states that models only need to fit a simple low-dimensional structured subspace, which is known as latent manifolds. You can interpolate between two inputs and move between the two spaces. Dr. Chen disagrees, saying this doesn't take into account adversarial attacks.

### Why DL Works?
In the beginning, all is randomness, with more training time the better the fit, but with too much training time, the model will fit itself to only the training data. Training data is the most important, with data curation and feature engineering being essential! The model needs to be trained on a dense sample, as a sparse sample will not allow the model to match the latent space and won't interpolate correctly.

## Training, Validation, and Test Sets
We use all three to train a model, and each have their own roles within the training loop.

### Information Leaks
Tuning a hyperparameter based on it's performance on the validation set, you leak information about the validation dataset to the model. 

### Evaluation Protocols
Holdout validation, K-Fold and Iterated K-fold Validation with Shuffling. The last is used when very little data is available, often in Kaggle. Method is to apply K-fold validation multiple times, shuffling the data before splitting it $K$ ways.

### Model Evaluation
Data representativeness is important, if the training data doesn't reflect the test data in some way, you won't be able to predict on those missing classes, the solution is to shuffle data before splitting into train/test sets.

Another issue is the arrow of time, which is a type of data leakage where the model basically gets a glimpse of the future. In this case, you should make sure the data in the testing set is posterior to the training data.

## Balancing Optimization and Generalization
Make sure to have some overfitting, and thus shows some generalization power, basically by beating a trivial baseline. From there, refine the generalization by fighting overfitting. The steps to achieve this are:

We first need to achieve overfitting, and to do that we need to solve three different problems. The first problem is that the model doesn't train, in that the training loss doesn't decrease. The solution is to look at the settings used in SGD, as this is not likely configured correctly. Look at the optimizer, learning rate, and batch size, as batch size likely needs to be increased, as a larger batch size will be less noisy and have more information. From there, we need to beat a common sense baseline, if we can't there is likely a fundamental problem, with either the data not containing sufficient information or the model isn't fundamentally suited to the problem at hand. If the situation is that we can't overfit, it likely means the model isn't complex enough for the problem, with the solution being to increase the size and complexity of the model until performance improves.

To improve generalization, we first need to look at the dataset, it is curve fitting, not magic. Spending time on data collection will be a better use of time than anything else. Going along with this, feature engineering is very important, imparting expert knowledge to the model. Early stopping is a powerful tool that will stop the training when the model loss stops improving, using the `EarlyStopping` callback (PyTorch has something similar). 

Regularizing the model is a series of techniques to actively make the model worse. Some of the regularization techniques are to make the network smaller, adding weight regularization, where the size of the weights is increased. Adding dropout will also help. With weight regularization, we use Occam's Razor, which in this case means use the simpler model when possible. With a simpler model, the distribution of parameter values will have less entropy, along with fewer parameters overall and those weights will have smaller values. Using a weight penalty like L1 or L2 will regularize the weights. Doing so on a larger model will be computationally prohibitive, and most larger models have too many parameters relative to the data, in that case dropout will be helpful.

## References
1. 
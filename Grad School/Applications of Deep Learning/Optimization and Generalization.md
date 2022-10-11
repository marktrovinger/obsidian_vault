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

## References
1. 
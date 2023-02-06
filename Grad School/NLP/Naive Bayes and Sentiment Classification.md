Classification is done as a supervised machine learning task.

## Naive Bayes
A very simple method for classification based on Bayes rule, using a simple representation of the document, a bag of words. 

### Classifier
$c_{MAP} = argmax P(c|d)$ 

We have the following assumptions:
Bag of Words assumption: Assume position doesn't matter
Conditional Indepence: Feature probabilites are independent

We do everything in log space, doesn't change the ranking, as the highest probability also has largest log probability. In its general form, is a linear classifier.

### Learning
First attempt would be use the maximum likelihood estimates, using the frequencies in the data. The main problem with this approach is that if we have a word unseen in its context, we can't wish away zero-probabilites! We can try to solve this using Laplace smoothing.

We first get the vocabulary from the document, calculate out the prior, and then calculate the likelihood terms.

### Unknown Words
How do we handle words that we haven't seen before? Ignore them!
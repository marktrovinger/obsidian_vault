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

## Sentiment Analysis - Optimization
Word occurence is more important than frequency

### Negation
Negation changes the meaning of a given word from positive to negative, one way to handle this is to add a NOT_ to every word between negation and following punctuation:

didn't like this movie -> did NOT_like this movie

### Lexicons
Pre-built word lists are called lexicons, example is the MPQA Subjectivity 

We use these by adding a feature that gets a count whenever a word from the lexicon appears.

## Other Tasks: Spam, Language ID


### Binary Multinomial Naive Bayes

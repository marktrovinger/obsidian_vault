# n-grams
Created: 2023-01-30 16:42
n-grams are part of a family of language models known as probablistic language models. The goal is to assign a probability to a sentence. 

## Applications
Used in spell check, as probablity of P(about fifteen minutes from) > P(about fifteen minuets from). Also used in spell check, as more common words and phrases appear more often. 

## Goal
The main goal is to compute the probablity of a sentence or sequence of words:
$P(W) = P(w_1, w_2, w_3, w_4, w_5...w_n)$ 

To compute a join probability, we can use the chain rule, which allows us to re-write our probabilities: $P(w_1)P(w_2|w_1)$ ...

We end up with:

$P(w_1,w_2,...w_n) = \prod P(w_i|w_{i-k}...w_{i-1}$   

## Markov Assumption
A simplifying assumption that says that the words before our word are not as relevant.

## Simplest Case - Unigram
A unigram model would be the simplest way to generate text, but it tends to come out as gibberish. 

## More Complex - Bigram
Better than unigram, but not much, conditioned on the previous 2 words instead of 1.

## N-Gram Models
Better than uni or bigram, but this is still insufficient, as there is a long-distance dependency problem in language.

## Estimating bigram probablities
Using Max Likelihood Estimate:
$P(w_i|w_{i-1}) = \frac{count(w_{i-1}, w_i)}{count(w_{i-1})}$ 

While we can use MLE to compute probablities for pairs of words, it can quickly underflow, which can be solved by moving to log space instead.

## Language Models
NLTK, KenLM, Google n-gram models

## Evaluation of N-gram models
Best practice is to put them in a task, doesn't matter what task, and compare how well they perform. For example run A and B in spelling correction task and compare results.

### Problems with this approach
The main issue with extrinsic evaluation is the time-consuming nature of this approach.

### Intrinsic Evaluation
Perplexity is the main metric, known as the Shannon Game: How well can we predict the next word? Unigram models are terrible, as they have no context length associated with them. Higher level n-gram models will perform better at this text.

## Generalization of Zeros


## References
1. https://www.nltk.org/
2. https://github.com/kpu/kenlm
3. 
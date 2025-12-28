## Model Simplifications
They focus on "attention-only" transformers, so no MLP layers, they have had troble in understanding MLP layers. They acknowledge that this is a weakness, but that they are working on it.

They ignore biases, for a couple of different reasons.

And they ignore layer norm.


## High-Level Arch

![[Pasted image 20230531140734.png]]

This is a residual block, with the residual stream being the line that goes from tokens to embed to $x_0$, to $x_i$, and so on. the attention heads $h_n$ read input from the residual stream and then write back to that same residual stream.

## Virtual Weights and the Residual Stream as a Communication Channel

### Definition  of Privileged Basis:
Privileged Basis vs Basis Free: A privileged basis occurs when some aspect of a model’s architecture encourages neural network features to align with basis dimensions, for example because of a sparse activation function such as ReLU. In a transformer, the only vectors with privileged bases are tokens, attention patterns and MLP activations. See the appendix table of variables for a full list of which activations have or don’t have privileged activations.

Some types of interpretability only make sense for activations with a privileged basis. For example, it doesn't really make sense to look at the "neurons" (ie. basis dimensions) of activations like the residual stream, keys, queries or values, which don't have a privileged basis. This isn't to say that there aren't ways to study them; a lot of interesting work is done on word embeddings without assuming a privileged basis (e.g. [11]). But having a privileged basis does open up helpful approaches.

#### VIRTUAL WEIGHTS
The idea here (I think) is that there are "virtual weights" that can connect any pairs of layers, as both are reading and writing from the same residual stream.

#### SUBSPACES AND RESIDUAL STREAM BANDWIDTH

### Analyzing a Two-Layer Model
What does a skip trigram look like for our decision transformer? Is this applicable?

### Induction Heads
"Learns" how a particular token is used and looks for the same usage of that token in the text. It can be much more confident in predictions because of this, and less vulnerable to shifts in distribution, as it doesn't depend on the learned statistics of a sample.

#### HOW INDUCTION HEADS WORK
Induction heads compute a key from tokens that are shifted one token back, this allows them to search for a key that is similar, but is one token forward. 

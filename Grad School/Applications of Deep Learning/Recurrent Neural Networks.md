# Recurrent Neural Networks
Created: 2022-11-17 10:45

## Time-series Data
Timeseries refers to any data that can be described as having a temporal component; weather data changes with time, as does financial data. 

## Recurrent Neural Network
Uses a *state* to maintain information relative to what it has seen before. Does this through the use of a recurrent relation from the output back into the RNN block.

## Stacking RNNs
Stacking multiple RNNs will increase the representational power of the model, and as long as you aren't overfitting, you are fine. Increasing network capacity is handled by increasing the number of units or number of layers. You need to use `unroll=True`, which will move computations for dropout onto the CPU, otherwise performance will suffer greatly.

## Bidirectional Recurrent Layers
These layers will present the same information to the RNN in a different way, which can increase accuracy. Refered to as the "Swiss Army Knife" of DL for NLP. Because of how order-dependent RNNs are, shuffling or reversing the timesteps can change the representations that an RNN extracts from that sequence.

## Performance Tuning for RNNs
First to try is to adjust the number of units in each recurrent layer, and the amount of dropout. Changing the learning rate used by the optimizer, or try a different optimizer altogether. You can also try using a stack of Dense layers as a regressor on top of the recurrent layers. Changing the sequence length, either shorter or longer can also improve performance. 
## References
1. 
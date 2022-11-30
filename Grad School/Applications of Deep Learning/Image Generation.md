# Image Generation
Created: 2022-11-29 10:49

# Key Idea
We want to develop a low-dimensional latent space of representations from existing images. In image generation, the module capable of mapping this latent point to a grid of pixels is known as a generator in GANs and an decoder in VAE. Generative adversial networks have the capability to be highly realistic. Variational autoencoders are very good at learning latent spaces that are well structured and continous, where specific directions encode a meaningful axis of variation in the data.

# Concept Vector
Certain directions in the space may encode interesting axes of variation in the original data.

# Autoencoders
There are two different loss functions used in VAEs; reconstruction loss, and regularization loss, with regularization loss helping to reduce overfitting.

## References
1. 
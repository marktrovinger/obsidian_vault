# Convolutional Neural Networks
Created: 2022-11-01 10:41

## Computer Vision
CNN (convolutional neural networks) first started getting good results on image classification tasks around 2015, such as ImageNet. They soon became dominant in the field, with pretty much all vision tasks using CNNs. 

### Conv2D
Both the inputs and outputs of a Conv2D are rank 3 tensors, with a shape of (height, weight, channels). From there, the number of channels for the output is determined by the filters argument. Each filter reflects a feature or pattern in a given image, with common filter sizes are $3 x 3$ or $5 x 5$, and the number of filters are a trainable weight w.r.t. backpropagation.
## References
1. Deep Learning With Python, Chapter 8
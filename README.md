# Transfer-Learning-for-Efficient-Net
In this project we implement the efficient net with the help of transfer learning idea.

### A brief introduction to Efficient Net
Efficient Net is an advanced neural network architecture and scaling method that uniformly scales all dimensions of depth/width/resolution using a compound coefficient. The EfficientNet models achieve both higher accuracy and better efficiency over existing CNNs, reducing parameter size and FLOPS by an order of magnitude. It is a lightweight model (can be used in android apps) and gives more accuracy even with less parameters.

In EfficientNet, we scale 3 components:
* Depth
* Width
* Resolution

The compound scaling method is justified by the intuition that if the input image is bigger, then the network needs more layers to increase the receptive field and more channels to capture more fine-grained patterns on the bigger image.

The base EfficientNet-B0 network is based on the inverted bottleneck residual blocks of MobileNetV2, in addition to squeeze-and-excitation blocks.

EfficientNets also transfer well and achieve state-of-the-art accuracy on CIFAR-100 (91.7%), Flowers (98.8%), and 3 other transfer learning datasets, with an order of magnitude fewer parameters.

### Implementation

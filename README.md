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
#### ***Preprocessing***
Firstly, we change the size of images to 244 * 244. Then we change the matrix of the pixels of each image to an array. Then, we change the dimension to 4 because the commands can only support this format. 
#### ***Creating the Efficient Network***
With the use of command 'EfficientNetB0' from Keras, we create the network. We use two taken images (A coffee mug and a water bottle). After creating the network, we use 'predict' for both of these images to show the estimations and their probabilities for each of the images. We just print the first three estimations that have higher probablities. 

### A problem with Efficient Network
If the input image isn't among the categories that the network can detect, then the output will not be valid. One simple solution to this problem is to consider a threshold for the estimations' probabilities. For example, a good threshold can be 0.15 or 15%. It means that if the probability value of the first estimation that has the highest probability is less than 0.15, then we should announce that the estimated output is not valid and it is not among the categories of this network. 

### Training the network woth a new dataset
For this part we use a dataset containing images of dogs and cats which are among the categories that can be detected by the network. We train the network by this dataset using early stopping and Adam optimizer. The results of accuracy values and validation accuracies plus the values of loss in each epoch has been reported and the related graphs are also plotted and shown in .ipynb file. 

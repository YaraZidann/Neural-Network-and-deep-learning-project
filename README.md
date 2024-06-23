# Neural-Network-and-deep-learning-project
Deep learning project using alot of architectures such as AlexNet, GoogleNet, ResNet, etc.
1-Data Preparation:
 DataLoader: 
Using Torch framework Dataset interface to create
CustomDataset class, then it is loaded into the dataloader torch 
class, it is an efficient way to load and iterate over the dataset, it 
provides Shuffling, Batching, Parallel Data Loading.
The CustomDataset class contains two main function.

1)load images function(),the functions consists of and if condition 
for specifying the type of learning (Train or Test),in case of test we 
store the images in an array and the labels in array of dummies 
because we don’t have the actual labels, in case of Train we do 
the same as we did in Test but the only difference is that we have 
the actual labels so the labels array is the Train labels. 
2)get_item function (), the function returns an image in batch of 
images after converting it to RGB and Transform.

 Data preprocessing: 
1. Normalization
2. RandomAugmentation: 
(It creates random Augmentation from flipping, rotation, 
changing colors, etc).
3. Resize
4. Randomerasing
(It removes portions of the image for more generalization).

2- Models:
a- AlexNet:
is the first CNN model, it is simple CNN, we changed the configuration of the
model from input size and kernel and pooling layers, this modification is used to
work with the small number of classes and small image size.

b- VGG:
 VGG model uses the first to use block concept, this block can contain a number
 of consecutive Conv layers then a pooling layer, this will stop the rapid decrease
 of the output size, and using 3x3 kernel also is computational efficient and better
 as it creates a deeper network. 

c- ResNet:
Resnet allow for increasing the complexity of the model without the draw back,
as it prove that the more complex model must have either the same solution or
better solution than the simpler model, this proven by considering a Class of F
containing all the function for an architecture, if f* is the true function, and fb is the
best function in F, now let's consider a more powerful architecture F', if the F ⊆ F'
then we can prove that F' can be either have the same solution or better, the arch
uses the idea of skip connection "identity function", this will ensure that adding a
new layer will make the arch either better or the same by choosing to learn the
identity or the ConvBlock.

d- GoogleNet:
GoogleNet uses multi-branch to create a stack of different perspectives of the
image, this capture detail at different extents, also removes the hyperparameter of
the kernel size as you use 1, 3, and 5 kernel size.

e- DenseNet: 
DenseNet uses the same idea as ResNet of skip connection, but adds the idea of Dense 
connectivity, it connects each layer to every subsequent layer in a feed-forward fashion in the 
same dense block.

f- MobileNet:
MobileNet is an efficient and portable CNN architecture that is used in real world 
applications. MobileNets primarily use depthwise seperable convolutions in place of the 
standard convolutions used in earlier architectures to build lighter models.MobileNets 
introduce two new global hyperparameters(width multiplier and resolution multiplier) that 
allow model developers to trade off latency or accuracy for speed and low size 
depending on their requirements.

g- Convnext:
ConvNext follows the design principles applied in “A ConvNet for the 2020s”, it 
combines best practices from predecessors such as ViT, MobileNet, and ResNext.

h- Ensamble model
i- Vision Transformer:
Vision Transformer replaces the use of CNNs by applying multi-head attention on image patches
coupled with MLP to model the global context of images, it attains excellent results when 
pretrained on large datasets (14M-300M images)

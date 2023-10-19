
![[Pasted image 20231019133907.png]]


## LeNet (1998)
![[Pasted image 20231012135819.png]]

Sub-Sampling - [[Pooling Layers#Max Pooling]]
- End-To-End idea
- Augmentation
- Convolution->Max Pooling loop

## ImageNet Dataset
- Large Scale Visual Recognition Challenge
- 1.000.000 multi-class images
- 1.000 classes

## AlexNet (2012)
![[Pasted image 20231012140549.png]]

- Made of 2 parts, because model could not fit on one graphics card xDDD
- [[RELU (Rectified Linear Unit)]], [[Augmentation in Deep Learning]], [[Dropout]]
- [[Gradient Descent with Momentum]]
- 2 GPU (5-6 days)

## VGG (2014) Very Deep Convolutional Networks For Large-Scale Image Recognition

### 5 Variations:
![[Pasted image 20231012140903.png]]
- Only 3x3 [[Convolution]]s (filters) (less than average) 
- [[Gradient Descent with Momentum]]
- [[Dropout]]
- Smart Initialization

## GoogLeNet (2014) / Inception. Going Deeper with Convolutions

- Number of channels decrease before heavy convolutions
- Several output layers for better trainability. 
- ImageNet error 6.67

![[Pasted image 20231012141837.png]]

### Projection layer (1x1 convolutions)
changes number of channels (RGB -> Black and White)
$$
new_{pixel} = <old_{pixel}, filter_{array}>
$$

### ResNet (2015) Deep Residual Learning for Image Recognition

#### Idea:
![[Pasted image 20231019134145.png| 450]]
- More layers makes worse training errors
- Although there is more possibility to over-train, but NN cant use it for some reason

#### Residual Connection
![[Pasted image 20231019134310.png]]

![[Pasted image 20231019134744.png]]

#### Results
- Low error on small layer size
- [[Gradient Descent with Momentum]], random weight initialization
- 4.49% Image Net


### Xception

![[Pasted image 20231019135148.png]]

- Разделение свертки по пространству и по каналам
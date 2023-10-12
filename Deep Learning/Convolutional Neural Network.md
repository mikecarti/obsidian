
# History
## LeNet (1998)
![[Pasted image 20231012135819.png]]

Sub-Sampling - [[Pooling Layers#Max Pooling]]
- End-To-End idea
- Augmentation

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
![[Pasted image 20231012141801.png|100]]

![[Pasted image 20231012141837.png]]



## Related
[[Image Generation with AI]]
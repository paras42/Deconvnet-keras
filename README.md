# Deconvnet
This is a implementation of Deconvnet in keras, following Matthew D.Zeiler's paper [Visualizing and Understanding Convolutional Networks](http://arxiv.org/pdf/1311.2901v3.pdf)

## Feature
Given a pre-trained keras model, this repo can visualize features of specified layer including dense layer.  

## Dependencies
* [Keras](https://github.com/fchollet/keras) 1.1(Theano Backend)
* Python >= 2.7
* argparse 1.0
* Pillow 1.1

## Examples
Below is several examples of feature visualization based on pre-trained VGG16 in keras, 'max' means pick the greates activation in the feature map to be visualized and set other elements to zeros, 'all' mean use all values in the feature map to visualize. <br />
The left is max activation feature, the right is all activation feature

* Original Image <p align="center">
<img height =224 src="husky.jpg">
</p>

* block3_conv3_128<p align="center">
<img height =224 src="results/block3_conv3_128_max.png" title = "max"> &nbsp; &nbsp; &nbsp; &nbsp; <img width=224 src="results/block3_conv3_128_all.png" title = "all">
</p>

* block4_conv2_46

The 46th feature in block4_conv2 layer catches 'nose' feature<p align="center">
<img height =224 src="results/block4_conv2_46_max.png" title = "max"> &nbsp; &nbsp; &nbsp; &nbsp; <img width=224 src="results/block4_conv2_46_all.png" title = "all">
</p>

* block5_conv3_256

The 256th feature in block5_conv3 layer catches 'ear' feature<p align="center">
<img height =224 src="results/block5_conv3_256_max.png" title = "max"> &nbsp; &nbsp; &nbsp; &nbsp; <img width=224 src="results/block5_conv3_256_all.png" title = "all">
</p>

* fc1_0 <p align="center">
<img height =224 src="results/fc1_0_all.png">
</p>

* fc2_248 <p align="center">
<img height =224 src="results/fc2_248_max.png">
</p>

* predictions_248 

predictions_248 is the predicted class of the image(label: Eskimo_dog) <p align="center">
<img height =224 src="results/predictions_248_max.png">
</p>

## Shortage
* The code implements visualize function for only Convolution2D, MaxPooling2D, Flatten, Input, Dense, Activation layers, thus cannot handle other type of layers.
* The code support only plain networks, thus cannot visualize ResNet, Highway Networks or something.

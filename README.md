# Neural Style Transfer with PyTorch

## Overview

This project aims to implement neural style transfer using PyTorch. Neural Style Transfer, an optimization technique, is employed to seamlessly blend the content of one image with the artistic style of another, resulting in an output image that retains the content image's features but is rendered in the style of the reference image.

## Project Objectives

1. Loading a pretrained VGG-19 model.
2. Extracting content and style features from images.
3. Creating style and content loss functions for optimization.
4. Minimizing the total loss to generate an artistic style image.

## How it works

Neural Style Transfer is structured as follows:

### 1: Loading VGG-19 Pretrained Model

First, load a pretrained VGG-19 model, a pivotal neural network used for feature extraction, serving as the foundation for the neural style transfer implementation.

### 2: Preprocess and Deprocess Image

For seamless integration with the VGG-19 model, it is imperative to preprocess images appropriately.
Following the generation of the stylized image, you need to deprocess it to obtain the final, visually pleasing result.

### 3: Get Content and Style Features, and Create Gram Matrix

Extract both content and style features from images while simultaneously creating a Gram matrix to capture intricate style details.

### 4: Create Content and Style Loss
In this project, several loss functions are utilized to guide the neural style transfer process. Here's an overview of the key loss 
#### `content_loss(target_conv4_2, content_conv4_2)`
The `content_loss` function calculates the content loss, which measures the difference between the content features of the target image and the content image. 

#### `style_loss(style_weights, target_features, style_grams)`
The `style_loss` captures the differences in style between the target image and the style image. It iterates through different layers and computes the mean squared difference between the Gram matrices of the target and style feature representations. The weights assigned to each layer control the importance of each layer's style contribution.

#### `total_loss(c_loss, s_loss, alpha, beta)`
The `total_loss` function combines the content and style losses to form the overall loss for optimization. It is a weighted sum of the content loss (`c_loss`) and the style loss (`s_loss`). The `alpha` and `beta` parameters determine the balance between content and style in the generated image.

### 5: Training Loop

The final step brings all the components together in a coherent training loop. That minimizes the total loss.


## Acknowledgements
Special thanks to Parth Dhameliya, the instructor at Coursera.org, for providing this project and valuable resources for understanding neural style transfar.


Certificate of Completion: [link](https://www.coursera.org/account/accomplishments/certificate/5Z6EHEXVASJ5)




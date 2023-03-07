# srgan
This repository is experimental implementation of "Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network" ( SRGAN )


https://arxiv.org/abs/1609.04802v5
<br/><br/><br/><br/>




# data

The model was trained with 800 DIV2k dataset.

You can download it from https://data.vision.ee.ethz.ch/cvl/DIV2K/

The model was tested with set5, and set14 dataset
<br/><br/><br/><br/>



# About SRGAN




SRGAN is a deep learning model used for image super-resolution, which is generating high-resolution images from their low-resolution counterparts. Previous deep learning-based methods for super-resolution typically focused on minimizing pixel-wise loss functions, such as mean squared error (MSE). However, this approach can lead to overly smooth images with poor perceptual quality since it encourages the model to find a pixel-wise average of the possible solutions. In contrast, SRGAN focuses on generating images with better perceptual quality by using Generative Adversarial Network and perceptual loss. 



![alt text](https://github.com/yys-1423/srgan/blob/main/data/image.png)

<br/><br/><br/><br/>

# Generative Adversarial Network (GAN)                           

Generative Adversarial Network (GAN) is model consisted of 2 networks, Generator Network and Discriminator Network. In SRGAN, The generator network produces high-resolution images from low-resolution input, while the discriminator network distinguishes generated images and original high-resolution images.This results in generator creating images with better perceptual quality
<br/><br/>

![alt text](https://github.com/yys-1423/srgan/blob/main/data/model.PNG)
<br/><br/><br/><br/>

# Perceptual loss

The loss function used in SRGAN is called perceptual loss, and it consists of 2 parts

![alt text](https://github.com/yys-1423/srgan/blob/main/data/loss.PNG)

The Adversarial loss is from GAN structure
<br/>

![alt text](https://github.com/yys-1423/srgan/blob/main/data/contentloss.PNG)

The content loss is defined as the Euclidean distance between the VGG19 feature representations of the generated output and the original high-resolution image. The use of content loss forces the network to be trained to produce images with better perceptual quality. This is because the deep VGG-19 feature maps extract high-level content information from the image, which helps the SRGAN network to focus on restoring a realistic image rather than relying solely on pixel-wise similarity.

<br/><br/><br/><br/>
# Results

Original HR image

![alt text](https://github.com/yys-1423/srgan/blob/main/data/hr1.png)
<br/>

x4 Low-resolution image

![alt text](https://github.com/yys-1423/srgan/blob/main/data/lr1.png)
<br/>

SRResNet

![alt text](https://github.com/yys-1423/srgan/blob/main/data/restnet1.png)
<br/>

SRGAN

![alt text](https://github.com/yys-1423/srgan/blob/main/data/sr1.png)
<br/><br/><br/><br/>

Original HR image

![alt text](https://github.com/yys-1423/srgan/blob/main/data/hr11.png)
<br/>

x4 Low-resolution image

![alt text](https://github.com/yys-1423/srgan/blob/main/data/ss11lr4.png)
<br/>

SRResNet

![alt text](https://github.com/yys-1423/srgan/blob/main/data/resnet11.png)
<br/>

SRGAN

![alt text](https://github.com/yys-1423/srgan/blob/main/data/sr11.png)
<br/>

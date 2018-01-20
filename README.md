# AI-Interior
AI-enabled Interior decoration app

Using Cycle GAN as discussed in [Unpaired Image-to-Image Translation using
Cycle-Consistent Adversarial Networks] (https://arxiv.org/abs/1703.10593) with
source code cloned and modified from [xhujoy/CycleGAN-tensorflow/]
(https://github.com/xhujoy/CycleGAN-tensorflow/)

We created and trained our own `texture2interior` model for this task.

## The Model
It is a mapping of unpaired images, created by extracting features of one image
and transforming and imposing them on another image. A one-to-one mapping
between images from input to target domain in the training set is very powerful
and can be used in variety of problems for solving real life problems. This is
achieved by a type of generative model, specifically a Generative Adversarial
Network dubbed CycleGAN. Here are some examples for this model (picture taken
from original paper)

![Sample models shown in paper](https://user-images.githubusercontent.com/31013555/35161803-46a3d952-fd67-11e7-8b87-bbca2191f245.jpg)

## Working Principle

![Model](https://github.com/hardikbansal/CycleGAN/raw/master/images/model.jpg)

![Generator](https://github.com/hardikbansal/CycleGAN/raw/master/images/Generator.jpg)

![Discriminator](https://github.com/hardikbansal/CycleGAN/raw/master/images/discriminator.jpg)

Above images are taken from the original paper

## Our model
We used tensorflow as backend for our model. We used resnet blocks for extracting
features.

Geenrator and Discriminator Genrator genrate genrator images by tranforming one
image feature to another image and discriminator does proofreading part (i.e.
check image genrated by generator is good or bad). The only way to fool
dicriminator if genrated recommendation for images is close to original.

It also checks for loss genrated by Genrator, Discriminator and by Cyclic Loss
during the training.

## Issues
Right now due to lack of computational power we were only able to train our
model upto 20 epoch (which was taking around 10 hours) on a single Nvidia GTX
1080, running TensorFloww 1.4 with Python 3.6 on Windows 10. We will update our
code as well as result, when we get better results.

Right now our model is able to detect edges, extracting features and partially
imposing on input image. The problem is lack of dataset for designing and with
solid colour palette because here we have to change mapping from interior to
solid colour palette because there is nothing to extract features from in a
solid colour palette.

Results observed were kind of good after 10 epochs with texture palette.
Features were being extracted and showing better result with it.

## NOTE
We will update this repositry as our model gets better.

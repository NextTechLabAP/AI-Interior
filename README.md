# AI-Interior
AI-enabled Interior decoration app

Using Cycle GAN as discussed in [Unpaired Image-to-Image Translation using
Cycle-Consistent Adversarial Networks] (https://arxiv.org/abs/1703.10593) with
source code cloned and modified from [xhujoy/CycleGAN-tensorflow/]
(https://github.com/xhujoy/CycleGAN-tensorflow/)

We created and trained our own `texture2interior` model for this task.

## CycleGAN Model
Its basically mapping of unpaired images by extracting features of one image and transforming and imposing them on another image.
A one-to-one mapping between images from input to target domain in the training set is very powerful and can be used in variety of problems for solving real life problems. This is achieved by a type of generative model, specifically a Generative Adversarial Network dubbed CycleGAN.Here are some examples for this model.

![Sample models shown in paper](https://user-images.githubusercontent.com/31013555/35161803-46a3d952-fd67-11e7-8b87-bbca2191f245.jpg)

## Working Principle of CycleGAN (MAP)

![Model](https://github.com/hardikbansal/CycleGAN/raw/master/images/model.jpg)

![Generator](https://github.com/hardikbansal/CycleGAN/raw/master/images/Generator.jpg)

![Discriminator](https://github.com/hardikbansal/CycleGAN/raw/master/images/discriminator.jpg)

Above images are taken from the original paper

## Our model 
We used tensorflow as backend for our model.we used resnet blocks for extracting features.
In our model we defind three function for getting and proof reading of genrated image by our model.
Genrator and Discriminator Genrator genrator genrator images by tranforming one image feature to anopther image and Discriminator does proof reading part i.e check image genrated by genrator is good or bad( in simple words). the only way to fool dicriminator if genrated recommendation for images is close 1.
It also checks for loss genrated by Genrator, Discriminator and by Cyclic Loss during the training part.

## Issues 
 Right now due to lack of computational power we were only be able to train our model upto max 20 epoch which was taking around 10 hours on one nvidia gtx 1080. we will update our code as well as result. when we will be getting better result.Right now our model is able to detect edges, extracting features and partially imposing on input image. the problem is lack of dataset for designing and with solid colour pallet because here we have to change mapping from interior to solid colour pallet because there is nothing to extract feature from solid colour pallet.
 Result was kinda good after 10 epoch with texture pallet feature was able to extract from it and showing better result with it.
 ## NOTE 
 we will update this repositry as our model gets better.
 

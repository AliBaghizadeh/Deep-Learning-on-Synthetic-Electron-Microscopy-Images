# Deep-Learning-on-Synthetic-Electron-Microscopy-Images

### Introduction
This project provides a conceptual journey into the use of most common deep learning architects like vgg, ResNet, Inception, etc., including image augmentation applied on high-resolution scanning electron microscopy (STEM) images of lattices which were created in another repository in my GitHub (**Synthetic-Microscopy-Images**).

The whole idea is to get a better sense of how to use powerful tools in machine learning on scientific problems and how they can help scientists to for example do less experimental work when it is not necessary which in turn results in saving the cost of project, time, and more importantly extract quantitative information out of the experimental data acquired by very expensive tools. 
I tried my best to build a decent database of images that mimics the real-world data, but I also noticed that some structures are close to each other and classes assigned to those structures will make the deep learning network confused. However, I have not corrected this as it allows curious people to experience what happens when there is a similarity between two or more classes in our image database. 

### Hardware and Software
The computer I used for this project is equipped to a 13th Gen Intel(R) Core(TM) i9-13900KF processor with 64 GB RAM, and NVIDIA GForce 4080 (Compute Capability 8.9) with 16 GB RAM. I found this configuration quite well for processing image datasets in medium size. <br><br>
To accomplish the project, I have used following packages:<br><br>
1- tensorflow-gpu  version 2.6.0  <br>
2- scikit-learn    version 1.2.1  <br>
3- Python          version 3.9.16 <br>
4- cudatoolkit     version 11.3.1  <br>

### Files and Instructions

1- ***random_lattice_split_data***:  <br>
&nbsp;&nbsp;&nbsp;This file will split your original dataset to train and valid folders. This approach is more suitable for using Image Augmentation generator of the Keras and &nbsp;&nbsp;&nbsp;in case you need to preserve the structure of the folder of the original images and classes. I recommend having a test dataset as well. <br>
2- ***random_lattices_vgg_ImageAug***: <br>
 &nbsp;&nbsp;&nbsp;This file applies image augmentation from keras.ImageAugmentation and then use pretrained weights of vgg model. This method is not memory friendly for large  datasets.<br>
3- ***random_lattices_vgg_tf_data_dataset***:  <br>
 &nbsp;&nbsp;&nbsp;This file applies image augmentation from tf.data.dataset on whole images, split data to train and valid datasets and then uses pretrained weights of vgg model &nbsp;&nbsp;&nbsp;for training a model with optional dense layers. This method is memory friendly for large datasets.<br>
4- ***random_lattices_ResNet50***: <br>
 &nbsp;&nbsp;&nbsp;This file applies image augmentation from tf.data.dataset on whole images, split data to train and valid datasets and then uses pretrained weights of ResNet50  &nbsp;&nbsp;&nbsp;model for training a model with optional dense layers. This method is memory friendly for large datasets.<br>

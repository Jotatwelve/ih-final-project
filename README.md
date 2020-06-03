<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100" align="right"/>
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTxJeCuB5k5HcKTOqvVG_-Te5_Uf11HwQRIeZAIeJGpdN9VC3Bo&usqp=CAU" alt="masked" width="100" align="left"/>



\
\
\
\
\


# IH Data Bootcamp - Final Project - Medical Mask Detection
*Jose "Jota" Angel Casado*

*Data Part Time Barcelona Dec 2019*


## Content
- [Project Description/Goal](#project_description)
- [Dataset](#dataset)
- [Workflow](#workflow)
    * [Preprocessing](#preprocessing)
    * [Crop and classification](#crop)
    * [Feature Engineering and Model Selection](#feature)
    * [Model](#model)
- [Results](#results)
- [Future Work](#fw)
- [Conclusions](#conc)
- [Links](#links)


<a name="project_description"></a>

## Project Description/Goal

Hello. My name is Jota and in this project, we're going to approach one of the main problems of our time. The mask. As we all know, not everyone has the same concept of security against the COVID-19 or popularly called CORONAVIRUS. 


We will try to create an algorithm to detect if a person, is wearing mask or not. This algorithm could be used like an alarm for security cameras in a shop or establishment to warn people to wear a mask or it will be useful to facial security checks at train stations if it is mandatory.


<a name="dataset"></a>

## Dataset

Initially, we are trying to work with different datasets:


   [Real-world masked face recognition dataset] --> https://drive.google.com/open?id=1UlOk6EtiaXTHylRUx2mySgvJX9ycoeBp



   [Pictures of people wearing medical masks] -->  https://www.kaggle.com/vtech6/medical-masks-dataset
   
   
  
   [Mask/No mask Dataset faces] -->  https://www.kaggle.com/ahmetfurkandemr/mask-datasets-v1
   
   
But finally we have worked with the **second dataset** because of the structure and size.
   
Our dataset contains pictures of people wearing medical masks along with XML files containing their descriptions.
There are images with over 3000 faces wearing masks and around 700 masks worn either wrongly or not worn at all. 

The XML files contain their locations and labels good, none or bad.

The dataset comes from Eden Social Welfare Foundation, Taiwan.


<a name="workflow"></a>

## Workflow


<a name="preproccesing"></a>

### Preprocessing

First of all we've obtained all the images names to assign every image with his own name.

Also we've obtained the image and label path to reassign the same name to both files. And return the new image and label path of the images.

After this initial part, we decided to parse the .xml files.

XML files contain their descriptions like their locations, bounding box and labels good, none or bad.

All the info that contains the xml files of each image help us to determine where to find all the people faces and if these people that we were analyzing are wearing medical masks or not.

#DESCRIPTION OF BOUNDING BOXES IN IMAGES:

#GREEN BOUNDBOX --> People wearing mask
#RED --> People not wearing mask
#BLUE --> People wearing mask but not properly weared


<a name="crop"></a>

### Crop and classification

After the first images and xml files exploration, we were cropping all the images only with people faces in each image.

We've obtained all the faces of people wearing and not wearing medical masks with the final goal to introduce these "cropped faces" in a model that allow us to distinguish automatically, people wearing mask or not.

After the crop process we classificate all the images in two labels:

0 --> PEOPLE WEARING MASK PROPERLY

1 --> PEOPLE NOT WEARING MASK

And the result was:

TOTAL OF FACES: 3788
Number of images good LABELED -0-: 3121
Number of images bad LABELED -1-: 667


<a name="feature"></a>

### Feature Engineering and Model Selection

Obtaining all the images that we want is time to decide which model can we use.

We have installed Torchvision package. This package consists of popular datasets, model architectures, and common image transformations for computer vision.

**Pre-trained models** are beneficial to us for many reasons. By using a pre-trained model we are saving time. Someone else has already spent the time and compute resources to learn a lot of features and our model will likely benefit from it.

The word pre-trained here means that the deep learning architectures, AlexNet, MobileNet, Resnet, for example, have been already trained on some (huge) dataset and thus carry the resultant weights and biases with them.

After all, and seeing many tutorials and blogs talking about the best pre-trained models, we've decided to use **Resnet50** because is the best models in terms of accuracy, inference time and model size comparing with other models like ResNeXt, VGG and others.

It is mandatory to study the problem of each project and decide which model works better with every different dataset and project.

<a name="model"></a>

### Model

Let's see our model parameters:

Dataset size:  3788
Train set size:  2272

Validation set size:  757
Test set size:  759

BATCH_SIZE = 20

LEARNING_RATE = 0.001

total_epoch = 20


FINAL EPOCHS OF OUR MODEL


EPOCH: 17 

Training Loss: 0.05358636488159618 

Validation Loss: 3.5607410681661804

Accuracy:  **0.9854689564068693**
            


EPOCH: 18  

Training Loss: 0.398578138448741  

Validation Loss: 2.0128642518747597  
            
Accuracy:  **0.9907529722589168**
            


EPOCH: 19 

Training Loss: 1.4577299662466388  
            
Validation Loss: 3.5445648041136337  
            
Accuracy:  **0.9841479524438573**



<a name="results"></a>

## Results

The final result of the model is:

**Accuracy: 0.9920948616600791**


<a name="fw"></a>

## Future Work

- Apply the same dataset to another models to see the different results and conclusions.


- Real time detection **(working on it)**


- Detect different types of masks (FFP1,FFP2...)


<a name="conc"></a>

## Conclusions

In our way to find a useful detector of people wearing medical masks or not, we have learned a lot of new things that made all of our resources and academic training make sense. This project can still be improved a lot, but my team and I have learned many new libraries, many new commands and have discovered new ways of working that we had not seen before.


We will still improve this project from these months onwards.


Thanks.


<a name="links"></a>

## Links


- https://www.pyimagesearch.com/2018/09/24/opencv-face-recognition/


- https://github.com/AIZOOTech/FaceMaskDetection


- https://github.com/X-zhangyang/Real-World-Masked-Face-Dataset


- https://docs.opencv.org/2.4/modules/contrib/doc/facerec/facerec_tutorial.html


- https://www.superdatascience.com/blogs/opencv-face-recognition


- Many of our code-along notebooks :)


# Keras AlexNet: Dog vs. Cat Classification
***Insert Alexnet Model Here***

I want to build a simple Deep Learning model for image classification on [Kaggle Dog vs. Cat Dataset](https://www.kaggle.com/c/dogs-vs-cats). In this project, I decided to use AlexNet architecture as it repeatedly mention during my Machine Learning course. This project is simple enough that helps me understand Alexnet, familiarize with Keras, and gain more experience in ML field.

## Dataset

![sample img](https://github.com/Insignite/Alexnet-DogvsCat-Classification/blob/master/img/2.PNG)

After download and extract dataset from zip file, let's view the data.
<img src="https://github.com/Insignite/Alexnet-DogvsCat-Classification/blob/master/img/1.PNG" height="65%" width="65%">


The dataset doesn't come with a label file. But I can extract the label from image name in train dataset.
<img src="https://github.com/Insignite/Alexnet-DogvsCat-Classification/blob/master/img/3.PNG" height="65%" width="65%">

 
I apply data generator to provide variety to our train dataset which definitely will improve the model accuracy. This also "replicate" real world dataset because not all input image will be a perfect picture of a dog or a cat. Let's view a sample from our generator.

<img src="https://github.com/Insignite/Alexnet-DogvsCat-Classification/blob/master/img/4.PNG" height="65%" width="65%">

The train dataset split as 80% training and 20% validation with image generator applied to both. Data now ready to be train.

## Deep Learning Model

As mentioned, I will be using AlexNet architecture to build the model. AlexNet consist of five convolutional layers, some followed by maximum pooling layers and then three fully connected layers. Since the dataset only consist of two classes (Dog and Cat), the last layer is a 2-ways softwax. 

| Layer name | Output | Filters | Kernel size | Stride | Padding |
|---|---|---|---|---|---|
| Input | 227x227x3 | - | - | - | - |
| Convol_1 | 55x55x96 | 96 | 11x11 | 4 | valid |
| MaxPool_1 | 27x27x96 | - | 3x3 | 2 | valid |
| Norm_1 | 27x27x96 | - | - | - | - |
| Convol_2 | 27x27x256 | 256 | 5x5 | 1 | valid |
| MaxPool_2 | 13x13x256 | - | 3x3 | 2 | valid |
| Norm_2 | 13x13x256 | - | - | - | - |
| Convol_3 | 13x13x384 | 384 | 3x3 | 1 | valid |
| Convol_4 | 13x13x384 | 384 | 3x3 | 1 | valid |
| Convol_5 | 13x13x256 | 256 | 3x3 | 1 | valid |
| MaxPool_3 | 6x6x256 | - | 3x3 | 2 | valid |
| FulConnect_1 | 4096 | - | - | - | - |
| FulConnect_2 | 4096 | - | - | - | - |
| FulConnect_3 | 1000 | - | - | - | - |
| FulConnect_4 | 2 (DogvCat) | - | - | - | - |

## Training
I am using a Huaweii Matebook Pro with 8th Gen Intel- i7, 16GB RAM, NVIDIA GeForce MX150. Definitely not a good laptop to run any type of machine learning project so each epochs take me roughly 10-15 minutes. I decided to use small epochs but reasonable enough to get decent result. I tried out with 3, then 10, and finally 20 epochs. If you have a stronger hardware, increase to 50 or so definitely will yield a good result.
<img src="" height="65%" width="65%">


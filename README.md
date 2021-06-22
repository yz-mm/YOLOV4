# YOLOV4

## Introduction

The full name of *YOLOV4* is *YOU ONLY LOOK ONCE*. It is an object detector which consists of a bunch of deep learning techniques and completely based on Convolutional Neural Network(CNN). The primary advantages of YOLOv4 compared to the other object detector are the fast speed and relatively high precision. 

The objective of Microsoft project 15 is detecting the gunshots in forest. The conventional audio classification method is not effective and efficient on this project, because the labelling of true locations of gunshots in training set is inaccurate. Therefore, we start to consider computer vision method, like YOLOV4, to do the detection. Firstly, the raw audio files are converted into thounds of 12 seconds clips and represented in Mel-spectrum. After that, according to the information of true locations of gunshots, the images that contain the gunshots are picked out and construct training data set. These pre-processing steps are the same with the other techniques used to do the detection for project 15 and you can find the detailed explanations from https://r15hil.github.io/ICL-Project15-ELP/.

In this project, YOLOV4 can be trained and deployed on NVIDIA GeForce GTX 1060 GPU and the training time is approximately one hour.


## Implementation

### Load Training Data

In order to train the model, the first step we need to do is loading the training data in yolov4-keras-master\VOCdevkit\VOC2007\Annotations. The data has to be in XML form and includes the information about the type of the object and the position of the bounding box.

Then run voc_annotations file to save the information of training data into a .txt file. Remember to modify the classes list in line 14 before operating the file.

<img src="https://github.com/yz-mm/YOLOV4/blob/main/image/ima1.jpg" width=75% height=75%>

### Train the Model

The train.py file is used to train the model. Before running the file, make sure the following file paths are correct.

<img src="https://github.com/yz-mm/YOLOV4/blob/main/image/ima2.jpg" width=75% height=75%>

### Test

Check the below link:
https://r15hil.github.io/ICL-Project15-ELP/howtorun.html

## More Explanations

The idea of using YOLOV4 is after training and testing faster r-cnn method. Faster r-cnn model achieves 95%-98% precision on gunshot detection which is extraordinarily improved compared to the current detector. The only potential problem is that the operation time of faster r-cnn algorithm 

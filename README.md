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

<img src="https://github.com/yz-mm/YOLOV4/blob/main/image/ima2.jpg" width=65% height=65%>

### Test

For more detailed testing tutorial, please check the below link :
https://r15hil.github.io/ICL-Project15-ELP/howtorun.html

## More Explanations

The idea of using YOLOV4 is after training and testing faster r-cnn method. Faster r-cnn model achieves 95%-98% precision on gunshot detection which is extraordinarily improved compared to the current detector. The training data for YOLOV4 model is totally same with that used in the faster r-cnn model. Therefore, in this document, the detection results of YOLOV4 will not be the main points to talk about. Briefly speaking, the YOLOV4 can achieve 85% precision but detect the events with lower probability than faster r-cnn.

<img src="https://github.com/yz-mm/YOLOV4/blob/main/image/img.jpgdetected_tir1100m_20180426_092825.wav_1560.0.png" width=50% height=50%><img src="https://github.com/yz-mm/YOLOV4/blob/main/image/imgtree3_20180517_000000.wav7416000.png" width=50% height=50%>

The reason why we still build YOLOV4 model is that it can make our clients to have diversified options and choose the most appropriate proposal in the real application condition.  Even though faster r-cnn model has the best detection performance, the disadvantage is obvious which is its operation time. In the case of similar GPU, the faster r-cnn needs 100 minutes to process 24 hours audio file while YOLOV4 only takes 44 minutes to do the same work.

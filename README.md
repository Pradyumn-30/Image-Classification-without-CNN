# Image-Classification-without-CNN
Classification of birds image

## Dataset Description

The dataset consists of colored images of different birds divided into three classes namely Cock of the rock, Northern cardinal, and Scarlet macaw. 
Images are of different sizes and dimensions and are of .jpg format. 
Every image has a different orientation of the bird which adds sufficient amount of variability in the dataset and makes the classification model more robust. 

Number of records for each bird are as follows:
Cock of the rock  ---> 124
Northern cardinal ---> 101
Scarlet macaw     ---> 105

Let's have a look on one of the images of these birds

## Spatial based Feature Extraction

The MATLAB code uses various predefined functions to obtain spatial domain-based features. imresize( ) resizes each image to 400 x 400 pixels.
mean( ) , median( ) and std2( ) are used to obtain mean, median, and standard deviation of the pixel values, rgb2gray( ) converts colored image to gray scale image. 
Edge detection is done by edge( ) function using Canny filter and threshold of 0.2. max( ) gives maximum of the pixel values, min( ) gives minimum of the pixel values and 
entropy( ) gives entropy of the image.

Pixel values above and below the mean color value are extracted using for loop and the extracted list of features are stored in a csv file using writematrix( ).

Note: In mydir variable you have to set the link of the MATLAB drive where you have stored the images.

## Frequency based Feature Extraction

First the image is converted to a gray scale image and stored in a structure.

Note: You can also convert to any of the three color channels and store in a structure. I have worked with gray structure.
Feel free to work with any of the three color structures. Code has been provided in the same file.

Fast Fourrier Transformation is applied to the gray scale image using fft2().
We compute mean, median, standard deviation, maximum, and minimum of the pixel values of the transformed image using mean( ), median( ), std( ), max( ), and min( ).
Storing the extracted features to a csv file using writematrix( ).

## Applying Discrete Cosine Transformation (DCT)

Coefficients are taken as features after applying DCT.

## Applying Haar Wavelet Transformation ( 3 levels ) and computing statistical measures.

Mean, median, standard deviation, maximum and minimum of pixel values are computed after applying Haar wavelet transformation.

## Normalization and Train-Test Split

Features may have very different ranges and hence feature values are normalized using MinMax scaler in Python 3.0.
Applying train test split to the data. ( 70% train and 30% test)

## Feature Description

## Classification

This is a multi-class classification problem with 3 classes.
Supervised learning algorithm like Support Vector Classifier is used for classification. 
Performance metric is accuracy. At the end results are compared.

Linear SVC is trained on the train data and evaluated on the test data.
SVC parametersis as follows--> kernel = 'linear', C = 100, class_weight = 'balanced'

A simple classification report gives the following results


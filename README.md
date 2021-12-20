# Face Recognition Project

![capturing](https://user-images.githubusercontent.com/65146994/146758720-82d28178-4827-4c1c-9aa8-ec5977360322.JPG)

## Description
In this project I modified one of [codebasics's project](https://github.com/codebasics/py/tree/master/DataScience/CelebrityFaceRecognition) to build simple Face Classification app for five Selected Indonesia's Actresses, Those are: 
1. Raisa Andriana
2. Isyana Sarasvati
3. Ariel Tatum
4. Maudy Ayunda
5. Pevita Pearce

## The Architecture
In a brief, this project has formed by two steps:

1. Building a model : In this section you preprocessing images for detecting face and eyes, as we know every person has an unique face and eyes shape. An image might contain multiple faces, also the face can be obstructed and not clear. The first step in our pre-processing pipeline is to detect faces from an image. After that we proprocessing the image using wavelet transform, In wavelet transformed image, you can see edges clearly and that can give us clues on various facial features such as eyes, nose, lips etc. For each image that you classified then we saved it in other folder as cropped images. Final step in this section is building machine learning model first using GridSearchCV to determine which model is the best fit for this problem, after that you split image data using `sklearn's train_test_split` in this case I use 90 % of training data and 10 % of testing data. Finally we saved the model in pickle's format.
2. Build Backend and Frontend model : In this section I build three main part of every website those are server : this folder contains server.py and util.py these two files works to enable html calls, also one folder named artifacts that contains columns.json that consists of name of provinces in json format and hdi.pickle that the saved ML model at the last. model : this contains model.py as a final file of ML model in first step above, model.pickle as a saved model in pickle's format and columns.json that consist of name of provinces in json format. client : this folder contains : app.html (which forms the structure of the website in html format), app.js (which helps html files in shaping and receiving data from machine learning processing) and app.css (this file contains the website design (such as color, text size, text type, etc.)

## How to use this app

1. First you should open the server folder and select the `server.py` file then run it, after that you will get a http call link.
2. Then you can open UI folder and found app.html file then double-click it.
3. After it runs, you can drag or select your test image for one of selected person in this model then click Classify. Please note that one image can be match by two images or more due to the model's accuracy.


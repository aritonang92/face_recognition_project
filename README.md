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
In a brief, this project has formed by this skeleton:

1. Image Preparation: Choose and download selected images that have clear face that consist of two eyes, one mouth and hair.
2. Data Cleaning: Using OpenCV to detect face and eyes using [haar cascades](https://docs.opencv.org/3.4/db/d28/tutorial_cascade_classifier.html) for every image
   .By using haar cascade I cropped face and eyes for every image and stored them in another folders.
3. Feature Engineering: Using wavelet transform that allows you to extract the important features from your images.
   Actually there are other feature extraction techniques as well but if you read and goo deeper for image processing
   literature, wavelet transform are often the most effective way of extracting features. Prior to understand
   the wavelet transform you have to know to understand the basic concept about [signal processing](https://www.youtube.com/watch?v=xrTor1uw5iI)
   and [Fourier transform](https://www.youtube.com/watch?v=spUNpyF58BY).
4. Train a model: In this modelling, I try Support Vector Machine method because it tends to perform good
   when it comes to many we're talking about classification. I have just randomly try that then I've tried
   couple of models using GridSearchCV abnd SVM performs the best. At the final step I saved the model in the pickle format.
5. Build Flask Server (Back end): In this step I have made a Python Flask server. Broadly speaking, 
   this section is the formation of the backend that we will use for the website later.
   By using a model that has been saved in pickle format, we use this to build a Flask server.
6. Build the website (Front end) : I've been using html, css and js to build a Front end. I used simple html
   css, and js to build an UI which will make a HTTP call to the back-end using jQuery.

## How to use this app

1. First you should open the server folder and select the `server.py` file then run it, after that you will get a http call link.
2. Then you can open UI folder and found app.html file then double-click it.
3. After it runs, you can drag or select your test image for one of selected person in this model then click Classify. Please note that one image can be match by two images or more due to the model's accuracy for each image.


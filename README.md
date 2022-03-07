# Face Recognition Project

![capturing](https://user-images.githubusercontent.com/65146994/146758720-82d28178-4827-4c1c-9aa8-ec5977360322.JPG)

## Description
In this project I build simple Face Classification app for five selected Indonesia's Actresses, Those are: 

1. Raisa Andriana
2. Isyana Sarasvati
3. Ariel Tatum
4. Maudy Ayunda
5. Pevita Pearce

## The Architecture
In a brief, this project has formed by this skeleton:

1. Image Preparation: Choose and download selected images for each actresses mentioned before that have clear face that consist of eyes, mouth, ears, hair, etc.
2. Data Cleaning: Performing data cleaning using OpenCV to detect face and eyes assisted by [haar cascades](https://docs.opencv.org/3.4/db/d28/tutorial_cascade_classifier.html) for every image
   .By using that I have cropped face and eye for every image and then stored them in another folders.
3. Feature Engineering: In this step I used wavelet transform that allows you to extract the important features from your images.
   Actually there are other feature extraction techniques as well but if you read and go deeper for image processing
   literature wavelet transform are often the most effective way of extracting features. Prior to perform
   the wavelet transform it's a good idea for you to have basic concept about [signal processing](https://www.youtube.com/watch?v=xrTor1uw5iI)
   and [Fourier transform](https://www.youtube.com/watch?v=spUNpyF58BY) because they are essential parts that you must know.
4. Train a model: Split the images data using `train_test_split` of `sklearn` library, in this particular case I tried
   90 % for training data and 10 % for testing data then I tried Support Vector Machine (SVM) method 
   because it tends to performs good when it comes to many we're talking about classification and also after
   tried couple of models using `GridSearchCV` and seems like SVM performs the best. In this modelling I got
   75.86 % of accuracy and if I compared to what [codebasics](https://github.com/codebasics/py/tree/master/DataScience/CelebrityFaceRecognition) did that got above 80 % of accuracy,
   my results is good enough because I used five female model instead of mixed male and female models and with various skin tone, this
   thing is matters when you're talking about image classification. At the final step I saved the model in the pickle format.
5. Build Flask Server for `server.py` and `util.py` (Back end): In this step I've made a Python Flask server. Broadly speaking, 
   this section is the formation of the backend that we will use for the website later by using a model 
   that has been saved in pickle format before. One thing that you should know
   in this section is at the part of classify image of `util.py` I introduced `base64` library 
   for converting an image into strings, simply I just drag my seleted image from local directory to [base64 decode](https://www.base64-image.de/)
   then they convert it into string.
6. Build the website (Front end) : I've been using simple html, css and js to build a Front end or UI which will make a HTTP call to the back-end using jQuery.

## How to use this app

1. First you should open the server folder and select the `server.py` file then run it, after that you will get a http call link.
2. Then you can open UI folder and found app.html file then run it.
3. After it runs, you can drag or select your test image for one of selected person in this model from your local directory
   then click Classify. Please note that one image might be match by two images or more due to the model's accuracy for each image.


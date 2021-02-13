# face_age_gender_detection
The system is able to detect face and recognize age &amp; gender of the persons in an image and in a video stream obtained from a camera in real time. Local Binary Pattern Histogram can recognize efficiently even if single training image is used for each person. Haar feature-based cascade classifiers in OpenCV approach for face detection. recognizer can recognize faces in different lighting conditions with high accuracy. Convolutional neural network models as caffe models it helps to recognize person age and gender.

INTODUCTION

Present information about the face, age, and gender detection system with real time video as an input. The working method of this system is entirely divided into two main modules. The face, age, and gender detection from the video is the first module while the tracking is the second module. To detect the face in the image, Face Name Graph Matching algorithm is used. This algorithm involves various methods such as Haar-Cascade method, Open-cv libraries etc. Face clustering algorithm is used for tracking the face in the video. This system is mainly designed for the security purposes. Video recorded in public areas for known person or suspicious activities are used as an input for the system. An automated facial recognition system was proposed using known Haar feature-based cascade classifier. This system will be able to detect face and recognize age and gender automatically in real time. System will identify and track one or more people captured in that video, this is taken as an output of this system.

Objective of the Project

•	To detect faces
•	To classify into Male/Female
•	To classify into one of the 8 age ranges
•	T0 put the results on the image and display it

A. Import the required modules
The Modules required to perform the facial recognition are cv2, os, image module and numpy. cv2 is the Open CV module and contains the functions for face detection and recognition. OS will be used to maneuver with image and directory names. First, we use this module to extract the image names in the database directory and then from these names individual number is extracted, which is used as a label for the face in that image. Since, the dataset images are in gif format and as of now, Open CV does not support gif format, Image module from PIL is used to read the image in gray scale format. Numpy arrays are used to store the images. 
B. Load the face detection Cascade, age and gender recognition model
To Load the face detection cascade the first step is to detect the face in each image. Once we get the region of interest containing the face in the image, we use it for training the recognizer. For the purpose of face detection, we will use the Haar Cascade provided by OpenCV. The haar cascades that come with OpenCV are located in the directory of OpenCV installation. Haar cascade frontal face default.xml is used for detecting the face. Cascade is loaded using the cv2 Cascade Classifier function which takes the path to the cascade xml file. if the xml file is in the current working directory, then relative path is used. In the dnn package, OpenCV has provided a class called Net which can be used to populate a neural network. Furthermore, these packages support importing neural network models from well-known deep learning frameworks like caffe, tensorflow and torch. CNN models as caffe models. Therefore, we will be using the CaffeImporter import that model into our application.Like the .prototxt files describe the network configuration and the .caffemodel file defines the internal states of the parameters of the layers.
C. Create the Face Recognizer Object  
The next step involves creating the face recognizer object. The face recognizer object has functions like FaceRecognizer.train() to train the recognizer and FaceRecognizer.predict() to recognize a face [13]. OpenCV currently provides Eigenface Recognizer, Fisherface Recognizer and Local Binary Patterns Histograms(LBPH) Face Recognizer. We used LBPH recognizer because Real life isn’t perfect. We simply can’t guarantee perfect light settings in your images or 10 different images of a person. LBPH focus on extracting local features from images. The idea is to not look at the whole image as a high-dimensional vector but describe only local features of an object. The basic idea of Local Binary Patterns is to summarize the local structure in an image by comparing each pixel with its neighbourhood. LBP operator is robust against monotonic gray scale transformations. 
D. Prepare the training set and Perform the training  
To create the function to prepare the training set, we will define a function that takes the absolute path to the image database as input argument and returns tuple of 2 list, one containing the detected faces and the other containing the corresponding label for that face. For example, if the ith index in the list of faces represents the 4th individual in the database, then the corresponding ith location in the list of labels has value equal to 4. Now to perform the training using the Face Detection. Train function. It requires 2 arguments, the features which in this case are the images of faces and the corresponding labels assigned to these faces which in this case are the individual number that we extracted from the image names.  
E. Testing   
For testing the Face, age and gender Recognizer, we check if the recognition was correct by seeing the predicted label when we bring the trained face in front of camera. The label is extracted using the os module and the string operations from the name of the sample images folder. Lower is the confidence score better is the prediction.

OUTPUT

Detecting face, eyes & mouth
![](https://github.com/Kiranashree23/face_age_gender_detection/blob/main/DETECT%201.png)
Description: This picture shows the detection of face, eyes, & mouth using openCV and haarcascade frontalface default, haarcascade eye, haarcascade mcs mouth classifier.



Detecting face in import image
![](https://github.com/Kiranashree23/face_age_gender_detection/blob/main/DETECT%202.png)
Description: This picture shows the detection of face in import image using openCV & haarcascade frontalface default classifier.



Detecting face, age, gender in live video.
![](https://github.com/Kiranashree23/face_age_gender_detection/blob/main/DETECT%203.png)
Description: This picture shows the detection of face, age and gender in live video using openCV & haarcascade frontalface default, Convolutional neural network models as caffe models it helps to recognize person age and gender.



Detecting face, age, gender in import image.
![](https://github.com/Kiranashree23/face_age_gender_detection/blob/main/DETECT%204.png)
Description: This picture shows the detection of face, age and gender in import dark lightning image using openCV & haarcascade frontalface default, Convolutional neural network models as caffe models it helps to recognize person age and gender.

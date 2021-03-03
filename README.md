# Iris: A Vehicle Safety Monitoring System
## Adam Lininger-White, Kevin Ayala, Ruben Pacheco-Caldera

![Image of Distracted Driver](https://github.com/rubeneezy/Iris/blob/main/Figure2_5-1024x629.jpg)



According to the CDC, 1.35 million people are killed on roadways around the world each year, caused by drunk driving, drowsiness, distracted driving, and or preventable mistakes such as not wearing a seatbelt. 

Seat Belt detection systems in cars can’t actually tell if someone is wearing theirs correctly, since they only detect whether it has been “clicked in''. Similarly, other measures such as the “hands on the wheel” heuristic attempt to provide a proxy for the information but may not solve the issue itself. 

By using computer vision to directly classify whether a person is actually wearing their seatbelt properly, or whether they are focusing on the road, we can provide much more useful data to insurance companies in the event of an at-fault scenario, and hopefully prevent these scenarios entirely with our application. 

In order to implement this system, we’ll have to find or generate an acceptable bank of images to use for classification. This may be a challenge, since we don’t think the specific application we are trying to build has been done. 

If we can get an 70% accuracy rating, we think that would make our project feasible, given the size of our data bank. Deployment of our system would happen as a web app where you can upload pictures and receive a response, but a reach goal would be to implement this as a part of the car’s system. 


![Image of Segmented Seatbelt](https://github.com/rubeneezy/Iris/blob/main/download.jpeg)


## Project Goals
1. Detect if all passengers are wearing seatbelts.
2. Detect drowsy drivers

## Literature Review

Kashevnik, A., Lashkov, I., Shilov, N., Ali, A., & 26th Conference of Open Innovations Association FRUCT, FRUCT 2020 26 2020 04 23 - 2020 04 24. (2020). Seat belt fastness detection based on image analysis from vehicle in-abin camera. Conference of Open Innovation Association, Fruct, 2020-april, 143–150. https://doi.org/10.23919/FRUCT48808.2020.9087474

The researchers set out to create a model that efficiently detects seatbelts. The model is based on the YOLO neural network architecture, as it is much faster and just as accurate to other architectures in many settings. Greyscaling images is a technique they used to normalize the image and avoid clothing color to interfere with training. They developed a model that could distinguish between the seat belt is fastened correctly, the seat belt is fastened behind the back, and the seat belt is not placed at all with 93% accuracy.


Chen, Yanxiang, et al. “Accurate Seat Belt Detection in Road Surveillance Images Based on Cnn and Svm.” Neurocomputing, vol. 274, 2018, pp. 80–87., doi:10.1016/j.neucom.2016.06.098.

This paper was using CNNs to detect whether seat belts were being worn, much like ours will. Most of the time, this depends on edge detection, however this paper argues that  it is not always dependable, since the type and layouts of cars differs. They’re able to extract more features using a model and then use those in a regressive model.

F. Vicente, Z. Huang, X. Xiong, F. De la Torre, W. Zhang and D. Levi, "Driver Gaze Tracking and Eyes Off the Road Detection System," in IEEE Transactions on Intelligent Transportation Systems, vol. 16, no. 4, pp. 2014-2027, Aug. 2015, doi: 10.1109/TITS.2015.2396031.

This paper introduces a system to monitor driver gaze and accurately detect when the driver’s eyes are on/off the road ahead. From the video stream of a small, inexpensive camera mounted on the steering wheel, the system captures a driver’s facial features and creates a 3D rendering of their head pose and gaze direction. With this information, the system detects eyes off road (EOR) with about 95% overall accuracy, and these results are consistent for drivers of different ages, sizes, colorings, eyewear (none, clear glasses, sunglasses), and conditions of illumination (spectrum from sunny days to nighttime). Importantly, the system’s use of geometric reasoning removes the need for major recalibration whenever there is a new driver or the camera position changes. 


Vural E., Cetin M., Ercil A., Littlewort G., Bartlett M., Movellan J. (2007) Drowsy Driver Detection Through Facial Movement Analysis. In: Lew M., Sebe N., Huang T.S., Bakker E.M. (eds) Human–Computer Interaction. HCI 2007. Lecture Notes in Computer Science, vol 4796. Springer, Berlin, Heidelberg. https://doi-org.ccl.idm.oclc.org/10.1007/978-3-540-75773-3_2

Here, they used 30 classifiers to detect various head and facial movements, such as yawning and blinking patterns. Unlike other research, they didn’t pre-assume anything about any of the features. So for example, they didn’t initially give any weight to blink rate, etc. They used unsupervised learning to track all of the features and have the system itself classify them drowsy. Using this method, they achieved 90% accuracy across subjects which they claim is the highest prediction rate reported to date for detecting real drowsiness. 

## Project Requirements
For this project, we will be using Pytoch and fastai to train our NN. We will use [State Farm's Distracted Driver Dataset on Kaggle.](https://www.kaggle.com/c/state-farm-distracted-driver-detection/overview) We will also train a convolutional NN as research on the topic suggests is the best performing for our use case. We want to experiment with both one-channel and three-channel images, and evaluate performance for both types of input. We will first focus on classification, thus our output will be a (1,1) vector containing the predicted class. We also want to consider segmentation later on, so we expect the output of this to be the same size of the input.


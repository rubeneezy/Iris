# Iris: A Vehicle Safety Monitoring System
## Adam Lininger-White, Kevin Ayala, Ruben Pacheco-Caldera

![Image of Distracted Driver](https://github.com/rubeneezy/Iris/blob/main/Figure2_5-1024x629.jpg)

### Introduction 
According to the CDC, 1.35 million people are killed on roadways around the world each year, caused by drunk driving, drowsiness, distracted driving, and or preventable mistakes such as not wearing a seatbelt. Seat Belt detection systems in cars cannot actually tell if someone is wearing theirs correctly, since they only detect whether it has been “clicked in’’. Similarly, other measures such as the “hands on the wheel” heuristic attempt to provide a proxy for the information but may not solve the issue itself. By using computer vision to directly classify whether a person is actually wearing their seatbelt properly, or whether they are focusing on the road, we can improve driver safety and provide useful information in the event of an at-fault scenario, and hopefully prevent these scenarios entirely with our application.

In order to implement this system, we’ll have to find or generate an acceptable bank of images to use for classification. This may be a challenge, since we don’t think the specific application we are trying to build has been done. If we can get an 70% accuracy rating, we think that would make our project feasible, given the size of our data bank. Deployment of our system would happen as a web app where you can upload pictures and receive a response, but a reach goal would be to implement this as a part of the car’s system.

### Related Works
There exists research around seatbelt detection. Since our application will run in real-time, performance is an important factor. Kashevnik et al. developed a seatbelt detection model using the YOLO neural network architecture, which provides significant performance boost and is optimized for real-time applications. Nonetheless, it is important not to sacrifice accuracy when improving performance. This model achieved a 93% accuracy, which is high enough for our use case.  Chen et al. used CNNs to detect whether seat belts were being worn, much like ours will. Most of the time, this depends on edge detection, however this paper argues that  it is not always dependable, since the type and layouts of cars differ. Their model is an amalgamation of two other models: one which exists to extract more features and one which actually trains using those new features. They argue that this is more effective. 

There is significant existing research around monitoring driver attentiveness. Many applications involve mounting cameras on the steering wheel, dashboard, or front seats to capture a video stream of the driver and their surroundings. F. Vicente et al. introduces a system to monitor driver gaze and accurately detect when the driver’s eyes are on/off the road ahead. The system captures a driver’s facial features and creates a 3D rendering of their head pose and gaze direction. With this information, the system detects eyes off road (EOR) with about 95% overall accuracy, and these results are consistent for drivers of different ages, sizes, colorings, eyewear, and conditions of illumination (spectrum from sunny days to nighttime). Importantly, the system’s use of geometric reasoning removes the need for major recalibration whenever there is a new driver or the camera position changes. Vural E. et al. used 30 classifiers to detect various head and facial movements, such as yawning and blinking patterns. Unlike other research, they didn’t pre-assume anything about any of the features. So for example, they didn’t initially give any weight to blink rate, etc. They used unsupervised learning to track all of the features and have the system itself classify them drowsy. Using this method, they achieved 90% accuracy across subjects which they claim is the highest prediction rate reported to date for detecting real drowsiness. 

The systems mentioned above were both simple to implement and remarkably successful in detecting driver focus and the presence of distracting objects. A logical next step, which seems feasible after surveying existing research, would involve piecing these safety measures together to create a more comprehensive driver safety/attentiveness system. 

## Implementation

We have gathered an initial set of about 200 images for training our seatbelt classifier. We have also started implementing simple versions of this classifier.

Although we have not yet gathered all of the images we plan to gather, we are unsure if 500 total images will suffice to train a good classifier. Again, there is no existing seatbelt dataset, so we have to stitch one up using existing datasets and our own data.


Chen, Yanxiang, et al. “Accurate Seat Belt Detection in Road Surveillance Images Based on Cnn and Svm.” Neurocomputing, vol. 274, 2018, pp. 80–87., doi:10.1016/j.neucom.2016.06.098.

F. Vicente, Z. Huang, X. Xiong, F. De la Torre, W. Zhang and D. Levi, "Driver Gaze Tracking and Eyes Off the Road Detection System," in IEEE Transactions on Intelligent Transportation Systems, vol. 16, no. 4, pp. 2014-2027, Aug. 2015, doi: 10.1109/TITS.2015.2396031.

Kashevnik, A., Lashkov, I., Shilov, N., Ali, A., & 26th Conference of Open Innovations Association FRUCT, FRUCT 2020 26 2020 04 23 - 2020 04 24. (2020). Seat belt fastness detection based on image analysis from vehicle in-cabin camera. Conference of Open Innovation Association, Fruct, 2020-april, 143–150. https://doi.org/10.23919/FRUCT48808.2020.9087474

Vural E., Cetin M., Ercil A., Littlewort G., Bartlett M., Movellan J. (2007) Drowsy Driver Detection Through Facial Movement Analysis. In: Lew M., Sebe N., Huang T.S., Bakker E.M. (eds) Human–Computer Interaction. HCI 2007. Lecture Notes in Computer Science, vol 4796. Springer, Berlin, Heidelberg. https://doi-org.ccl.idm.oclc.org/10.1007/978-3-540-75773-3_2

## Methods

### Development Setup
- We will be using Pomona's HPC servers to train our neural networks.

### Software
- To train and run our model, we are considering using fastai and pytorch because we are already familiar with these, but we will also investigate and experiment with using some of the software and NN architectures in the papers.
- We are using a CNN.
- We will experiment using transfer learning using existing pre-trained models such as AlexNet.
- If we get to implement this tool in real-time seatbelt detection, we have to optimize the speed of our application.
- We plan to investigate different deployment options for a web application version of this application.

### Data Collection
- We are taking a hybrid approach between using existing images and supplementing with our own.
- We are taking pictures of ourselves, family, and friends, and varying the conditions of the images.
- We plan to experiment with image preprocessing methods such as greyscaling, mirroring images, and other methods.
- We are all physically similar, and thus our data collection will be biased, even with varying conditions.
- This model may work only for college-aged, light-skinned people.



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

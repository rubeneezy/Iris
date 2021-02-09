# Iris: A Vehicle Safety Monitoring System

## Project Description
According to the CDC, 1.35 million people are killed on roadways around the world each year. Many of these accidents are caused by drunk driving, drowsiness, distracted driving, and many others by preventable mistakes such as wearing a seatbelt.

I propose to build Iris, a computer vision system that uses Neural Networks to monitor passenger and driver behavior to minimize the probability of injury in case of an accident. Iris will warn passengers if it spots any safety concerns such as a) not wearing a seatbelt b) driver is distracted (gazing away) c) driver is drowsy. A neural network will be trained for each one of these warnings and all will be deployed in new environments to run in parallel to create the full Iris system. Iris will be ran on an Nvidia Jetson Nano to provide portable convinience and will eventually be tested live.

The dataset for seatbelt detection may need to be created (there exists one on imagenet but not sure how to access it). However, many datasets exist for driver gaze and drowsiness detection. Although Iris may be ambitious given the limited timeline, it is nonetheless possible with enough people working on it. The Minimum Viable Product of Iris is at least one safety detection feature implemented.

### The Potential of Autonomy
Autonomous vehicles have the potential to reduce the number of driving accidents yet seatbelt wear and other safety precautions need to remain in place. In addition, many of the current advanced driver systems such as Tesla require a safety driver, thus additional safety monitoring is needed. Iris has significance and plays a part in the advancement of autonomous vehicles.

## Project Goals
1. Detect if all passengers are wearing seatbelts.
2. Detect safety driver gaze (to prevent distractions).
3. Detect extraordinary safety driver conditions such as drowsiness/sleepiness.

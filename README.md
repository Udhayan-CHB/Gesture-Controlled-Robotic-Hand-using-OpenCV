# Gesture-Controlled-Robotic-Hand-using-OpenCV
A vision-based robotic arm that responds to real-time hand movements. This project uses computer vision to detect gestures and translates them into physical arm motions, enabling intuitive, contactless control.

# Features

- Real-time hand gesture recognition using OpenCV
- Maps gestures to robotic arm movements
- Smooth and responsive control
- Low-cost setup using a webcam and basic components

# Tech Stack

- Language: Python
- Computer Vision: OpenCV
- Hand Tracking: Mediapipe 
- Hardware: Arduino Uno/Nano, Servo Motors, Robotic Arm Frame
- Communication: Serial (USB) between Python and Arduino

# Hardware Requirements

- 1x Arduino Uno/Nano  
- 5x Servo motors (for basic arm movement)  
- Robotic Arm (custom or off-the-shelf)  
- USB cable for Arduino  
- Webcam  
- Jumper wires and breadboard  

 # Software Requirements

- Python 3.x  
- OpenCV  
- Mediapipe (optional but recommended for better hand tracking)  
- PySerial  
- Arduino IDE  

# How It Works

1. OpenCV captures real-time video from your webcam.  
2. Hand gestures are detected using contour/landmark tracking.  
3. The gesture is mapped to a specific command.  
4. Command is sent via serial to Arduino.  
5. Arduino interprets the command and actuates the robotic arm using servo motors.



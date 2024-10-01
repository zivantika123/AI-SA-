# Gym Pose Estimation

The model is https://teachablemachine.withgoogle.com/models/k4U33q8co/

This project uses pose estimation techniques with TensorFlow.js and Teachable Machine to track and classify gym exercises, including lunges, plank, pull-up, squat, and crunches. Users can interact with the system through either a live webcam feed or uploaded photos.

## Table of Contents
- [Description](#description)
  - [Project Goals](#project-goals)
  - [Technologies Used](#technologies-used)
- [Features](#features)
  - [Real-time Pose Detection](#real-time-pose-detection)
  - [Photo Upload Option](#photo-upload-option)
  - [Exercise Classification](#exercise-classification)
- [Installation](#installation)
  - [Prerequisites](#prerequisites)
  - [Clone the Repository](#clone-the-repository)
  - [Download and Setup Model](#download-and-setup-model)
- [Usage](#usage)
  - [Using Webcam](#using-webcam)
  - [Using Photo Upload](#using-photo-upload)
  - [Exercise Feedback](#exercise-feedback)
- [Supported Exercises](#supported-exercises)
  - [Lunges](#lunges)
  - [Plank](#plank)
  - [Pull-Up](#pull-up)
  - [Squat](#squat)
  - [Crunches](#crunches)
- [Model Overview](#model-overview)
  - [Training the Model](#training-the-model)
  - [Teachable Machine Integration](#teachable-machine-integration)
  - [Accuracy and Confidence Scores](#accuracy-and-confidence-scores)
- [Code Structure](#code-structure)
  - [HTML](#html)
  - [CSS](#css)
  - [JavaScript](#javascript)
    - [Model Initialization](#model-initialization)
    - [Webcam Setup](#webcam-setup)
    - [Pose Detection](#pose-detection)
    - [Exercise Classification](#exercise-classification)
- [Dependencies](#dependencies)
  - [TensorFlow.js](#tensorflowjs)
  - [Teachable Machine Pose Library](#teachable-machine-pose-library)
- [Future Improvements](#future-improvements)
  - [Additional Exercises](#additional-exercises)
  - [Performance Optimization](#performance-optimization)
  - [Mobile Support](#mobile-support)
- [License](#license)

  Explaination

  Description

The Description part of the README provides an overview of the Gym Pose Estimation project. It introduces the project as a tool designed to help users track their gym workouts by detecting and analyzing their exercise form using either a webcam or a photo upload. This section briefly explains that the system can identify exercises like lunges, squats, planks, pull-ups, and crunches, providing real-time feedback or analysis from uploaded images. The goal of this section is to clearly communicate what the project does and how users can benefit from it.


---

Project Goals

In the Project Goals section, the objectives of the project are laid out. These goals typically include:

Providing real-time feedback on exercise form to help users perform exercises more accurately.

Improving workout experience by allowing users to track their progress through pose estimation.

Supporting multiple exercises for a well-rounded gym workout experience.

Enabling photo-based feedback, offering flexibility for users who cannot use the webcam or prefer using photos to track their exercise form. This section focuses on the practical benefits of the system and the user’s perspective, explaining why the project exists and how it aims to improve workout efficiency.

Technologies Used

The Technologies Used section lists and explains the tools and technologies involved in creating the project. This could include:

TensorFlow.js: A JavaScript library used to run the machine learning model in the browser. It's responsible for performing the real-time pose detection and classification using deep learning.

Teachable Machine: A Google-powered tool that allows users to train machine learning models easily. In this project, it’s used to train a pose estimation model capable of classifying different exercises based on the user’s body movements.

HTML, CSS, and JavaScript: These are the core web technologies used to build the user interface.

HTML structures the page, placing elements like the webcam stream and buttons.

CSS styles the interface, ensuring that the application looks visually appealing.

JavaScript handles the logic, such as webcam setup, pose detection, and model integration.


Features

The Features section outlines the key functionalities of the Gym Pose Estimation project. This part is critical for users to understand what the system is capable of doing and how it stands out. Each feature is explained to provide clarity on how it benefits users, making the system practical and efficient for exercise tracking.


---

Real-time Pose Detection

This feature allows users to get live feedback on their exercise form by using their webcam. The system continuously tracks and analyzes body movements in real-time as the user performs different exercises. Key points of the body, like joints and limbs, are detected, and the system provides immediate feedback on how well the user is executing the exercise. This feature is particularly useful for people who want to improve their workout form, ensuring that they are doing each exercise correctly and avoiding injury.

In technical terms, this involves using TensorFlow.js to capture frames from the webcam and run them through the machine learning model trained to detect specific poses. The system draws keypoints and skeletons on the user's body in the video stream, offering visual and textual feedback on the current pose and exercise being performed.

Photo Upload Option

Not everyone may have access to a webcam or prefer using it, so the Photo Upload Option provides an alternative. Users can upload a photo of themselves performing an exercise, and the system will analyze the image to detect the pose and provide feedback just as it would with real-time detection. This adds flexibility and convenience, making the project more accessible to a wider range of users.

This feature works by allowing users to upload an image, which is then processed by the model in a similar way to real-time detection. The uploaded image is fed into the model, and the same pose estimation algorithm is used to classify the exercise and evaluate the pose accuracy. The system then returns feedback on the exercise, based on the model’s classification.


Exercise Classification

The Exercise Classification feature is central to the project. Once the system detects the user’s body pose, it classifies the exercise being performed, such as lunges, planks, squats, pull-ups, or crunches. This classification allows the system to give targeted feedback, letting users know not only what exercise they are doing but also how well they are doing it.

Installation

Prerequisites

Before starting the installation, ensure you have the following:

A modern web browser like Chrome, Firefox, or Safari that supports WebRTC (for webcam access).
A working webcam (if you plan to use the webcam feature for real-time exercise tracking).
An internet connection to access the TensorFlow.js and Teachable Machine libraries (or you can include them locally in the project if needed).
Basic knowledge of how to work with HTML, JavaScript, and possibly simple server setups if running locally.
Clone the Repository
To start working with the project locally, clone the repository to your machine. Open a terminal or command prompt and run the following command:

bash
Copy code
git clone https://github.com/yourusername/gym-pose-estimation.git
This will download the project files into a directory on your system.

Once cloned, navigate to the project folder:

bash

cd gym-pose-estimation
Download and Setup Model
The Teachable Machine model for pose estimation needs to be downloaded and placed in the appropriate directory within the project.

Download Model:
Go to the Teachable Machine model page or the export panel, and download the following files:
model.json
metadata.json
Weight files (if applicable, these could be .bin files).

Setup Model in Project:

Create a folder called model/ in the root directory of your project.
Place the model.json, metadata.json, and all associated weight files inside the model/ folder.
Model Path: Ensure that the paths in your JavaScript file (usually in the index.html) correctly point to the model directory. For example:
javascript

"const modelURL = './model/model.json';"
"const metadataURL = './model/metadata.json';"

Once everything is set up, open the index.html file in your browser to run the project. You can do this either by directly opening the file in your browser or using a local server like http-server or Live Server for better results.



Usage
Using Webcam
To track your exercises in real-time using your webcam, follow these steps:

Start the Webcam:
Open the project in your browser by launching the index.html file.
Click the "Start Webcam" button to give the browser access to your webcam.
Webcam Access:
The browser will prompt you to allow access to your webcam. Approve this to start capturing video.
Live Pose Detection:
Once the webcam is active, the system will start capturing frames and detecting your poses in real-time.
The detected exercise (e.g., lunges, plank) and its corresponding confidence score will be displayed in the output section.
Ensure you have enough lighting and space for the webcam to clearly capture your movements.
Using Photo Upload
If you prefer to upload a static image for pose estimation instead of using the webcam, follow these steps:

Select an Image:
On the homepage, find the "Upload Photo" button and click on it.
Upload Photo:
Choose an image from your local system that shows your body clearly performing an exercise (like a squat, plank, etc.).
Pose Detection:
Once the image is uploaded, the system will process the image and identify the pose.
The detected exercise and its confidence score will be displayed below the image.
This feature is useful when you want to analyze your form from previously captured photos or if you are unable to use the webcam.

Exercise Feedback
The system provides real-time feedback on your exercises, including:

Detected Exercise:
Based on your pose, the system will classify the exercise (e.g., "Squat", "Plank").
Confidence Score:
A confidence score (between 0 and 1) will indicate how certain the system is in its classification. For example, Squat: 0.95 means a 95% confidence in the detection of a squat.
Form Feedback:
Optional: The system could provide basic form suggestions or corrections (e.g., "Keep your back straight" or "Lower your knees").
Continuous Tracking (Webcam):
If using a webcam, feedback will update continuously as you perform different exercises, adjusting for each repetition.
Supported Exercises
The pose estimation model supports the detection of five core exercises:

Lunges

Description: Lunges are a lower-body exercise where one leg is stepped forward while lowering the body until the knee of the rear leg nearly touches the ground.
Detection: The system detects the forward leg, bent knees, and upright posture.
Plank

Description: A plank is a core-strengthening exercise where the body is held in a straight position parallel to the ground, supported by the forearms and toes.
Detection: The system identifies a straight body line, shoulder and hip alignment.
Pull-Up

Description: Pull-ups are an upper-body exercise where you lift your body by pulling on a horizontal bar until your chin is above the bar.
Detection: The system looks for raised arms and body position during the pull-up movement.
Squat

Description: Squats are a fundamental leg exercise where you lower your hips from a standing position and then return to standing.
Detection: The system detects the bend in the knees and hips, and the posture of your upper body.
Crunches

Description: Crunches are an abdominal exercise where you raise your upper body towards your knees while lying on your back.
Detection: The system identifies the flexion of the torso and the bend in the upper body during the crunch.
These exercises have been selected for their distinct postures, making them ideal for pose estimation and feedback.

Model Overview
Training the Model
The pose estimation model was trained using Teachable Machine, a web-based tool that allows users to build machine learning models quickly without needing advanced programming knowledge.

Data Collection:

To train the model, several images or webcam data were captured for each exercise (lunges, plank, pull-up, squat, and crunches). The more data collected, the better the model's performance in recognizing these poses.
Pose Estimation:

The training focuses on keypoints detection using PoseNet (or another pose estimation algorithm) that identifies specific body joints, like shoulders, elbows, knees, and ankles.
Labeling:

Each exercise (e.g., "Squat") is labeled, and the model learns to associate body positions with these labels. It uses the labeled data to predict and classify exercises during real-time inference.

Teachable Machine Integration

This project integrates the model created using Teachable Machine. Here’s how it works:

Exporting the Model:
Once the model is trained on Teachable Machine, it can be exported as a set of .json files and weights files.
Loading the Model:

The exported model (consisting of model.json, metadata.json, and weight files) is loaded into the project using the Teachable Machine Pose Library.

Integration in JavaScript:

The model is integrated directly into the HTML and JavaScript code. Using the tmPose library, the model is initialized and used for real-time pose detection, either through a webcam or an uploaded image.

Accuracy and Confidence Scores

The model outputs both the classified exercise and its confidence score, reflecting how certain the model is about its prediction.

Confidence Scores:

The confidence score is a probability between 0 and 1. For example, a score of 0.92 for "Squat" means the model is 92% confident that the current pose matches a squat.
Accuracy:

The overall accuracy of the model depends on how well it was trained. The more diverse the training data (e.g., various angles, lighting conditions), the higher the accuracy during real-world use.
Continuous Prediction (Webcam):

During webcam usage, the model constantly makes predictions as you move through exercises, updating the confidence scores in real-time.
Model Initialization
The first step in JavaScript is initializing the Teachable Machine model:

Loading the Model:
The model is loaded using tmPose.load() where the URLs for model.json and metadata.json are specified.
Model Ready:
Once the model is loaded, the system is ready to start making predictions on images or webcam data.
Webcam Setup
The webcam setup ensures that the user's camera is accessed and the video feed is captured for real-time pose detection:

Webcam Initialization:

The webcam is initialized with the specified dimensions (e.g., 200x200) and optional flipping (for mirror effect).
Play Function:

The webcam.play() method starts the video feed, which is then continuously updated as the user performs exercises.
Pose Detection
The pose detection part uses the loaded model to analyze the webcam or image data and estimate the user's pose:

Pose Estimation:

The model.estimatePose() function is used to estimate keypoints on the body. These keypoints include critical joints like elbows, knees, and shoulders.
Keypoint Drawing:

The detected keypoints are drawn on the canvas using the drawKeypoints() function, visualizing the pose detected in real-time.
Exercise Classification
Once the pose is detected, the model classifies which exercise the pose represents:

Prediction:

The model.predict() function classifies the current pose into one of the predefined exercises (e.g., lunges, squat).
Display Results:
The classified exercise and its confidence score are displayed on the webpage, allowing the user to see feedback in real-time as they perform the exercise.

Dependencies
TensorFlow.js
TensorFlow.js is the core library used for machine learning in the browser.

Purpose:

TensorFlow.js allows the model to run directly in the user's browser without the need for server-side computation. This enables real-time pose estimation using the webcam or uploaded images.
Integration:

It is imported via a CDN (Content Delivery Network) link, which makes it easy to add to the project. The library handles the computational tasks necessary for processing the pose estimation model and classifying exercises.
Version:

The project uses TensorFlow.js version 1.3.1, but it can be updated to a more recent version for better performance and support for additional features.
Teachable Machine Pose Library
The Teachable Machine Pose Library is built on top of TensorFlow.js and provides an easy interface for using pose estimation models.

Purpose:

This library simplifies the integration of pose estimation models trained using Google’s Teachable Machine. It takes care of loading the model, making predictions, and estimating poses.
Integration:

The library is included via a CDN and is crucial for processing the webcam feed or uploaded images and generating predictions related to exercise poses.
Pose Detection:

It enables the real-time detection of poses by identifying body joints and classifying them into predefined categories (like squats or lunges) based on the trained model.
Future Improvements

Additional Exercises:

Currently, the system supports five core exercises (lunges, plank, pull-up, squat, and crunches). Future versions of the project could include additional exercises to cover a wider range of workout routines.

Exercise Variety:

Future improvements may involve training the model to recognize additional exercises such as push-ups, jumping jacks, and deadlifts.

Custom Exercises:

Users may also have the option to train the model with their own custom exercises by using Teachable Machine or other machine learning tools, adding flexibility to the system.
Performance Optimization
To improve the speed and responsiveness of the system, various performance enhancements can be made:

Webcam Frame Rate:

Adjusting the frame rate of the webcam feed can ensure smoother and more accurate pose detection, especially for faster movements.
Model Efficiency:

Optimizing the model’s architecture or using a lightweight version of PoseNet could help reduce the computational load and improve the real-time feedback speed.

Asynchronous Processing:

Utilizing asynchronous JavaScript for pose detection and classification could help reduce latency, allowing for quicker feedback while performing exercises.
Mobile Support
Currently, the system is primarily designed for desktop use. However, future iterations could focus on optimizing the interface and functionality for mobile devices.

Responsive Design:

A mobile-friendly layout and interface would allow users to perform exercises and get feedback using their phone's camera, making the system more portable and accessible.
Mobile Browser Optimization:

Ensuring compatibility with mobile browsers and handling camera access properly on different devices (iOS and Android) would enhance user experience on smartphones.

App Development:

Eventually, the project could be turned into a mobile app with offline support, allowing users to train and get feedback without needing an active internet connection.


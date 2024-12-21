# Body Landmarks Detection using MediaPipe Library

## Project Summary

This project focuses on detecting and visualizing human body landmarks using the **MediaPipe** library, a powerful tool for real-time computer vision tasks. The primary goal of the project was to detect full-body landmarks, hand landmarks, and face landmarks in video files, and to visualize these landmarks for further analysis. The project uses the **MediaPipe Holistic Model**, which is capable of recognizing a wide range of human body, hand, and face landmarks from video frames. The output was an annotated video that displays these landmarks in real-time, with the option to visualize them as static points or connected by lines.

## 1. Project Overview

The ability to detect and track human landmarks (such as body joints, hands, and facial features) in video frames has a wide array of applications in fields such as sports analysis, human-computer interaction, animation, and health monitoring. This project leverages **MediaPipe**, an open-source library developed by Google, which provides pre-trained models to detect landmarks efficiently. The project's goal was to implement a system capable of processing a video, detecting body landmarks, and outputting the video with these landmarks visualized.

### Objectives

- **Detect Full-Body Landmarks**: Use MediaPipe's holistic model to track human body landmarks (e.g., shoulders, elbows, hips, knees, etc.).
- **Visualize Landmarks**: Draw the landmarks and their connections on the video to provide a clear visual representation.
- **Process Video Files**: Enable video processing with real-time performance and save the annotated video.
- **Hands and Face Landmarks**: In addition to body landmarks, detect and display hand and face landmarks in the video.

## 2. Methodology

### 2.1. Tools and Technologies Used

- **MediaPipe**: A cross-platform framework for building multimodal applied machine learning pipelines, providing a holistic model for full-body landmark detection.
- **OpenCV**: A computer vision library used to handle video input/output, image processing, and visualizations.
- **NumPy**: A library for numerical computations, which was used for frame manipulation.
- **Google Colab**: An online platform that provided the computing environment for running the project and displaying the processed videos.

### 2.2. Approach

#### 2.2.1. Video Input Handling

The first step in the process was to initialize video capture using OpenCV’s cv2.VideoCapture. The system opens the video file, extracts important properties such as frame dimensions and frames per second (FPS), and sets up an output video file with the same properties to save the processed frames.

#### 2.2.2. Landmark Detection

The core of the project is the **MediaPipe Holistic** model, which provides accurate landmark detection for the body, hands, and face. For each frame in the video, the frame is processed using this model, and the system detects and returns the coordinates of key landmarks. These landmarks are then visualized by drawing circles and connecting lines between related landmarks.

#### 2.2.3. Visualization

The body landmarks are drawn on a black canvas (as a separate layer) where:
- **Circles** are drawn for each detected landmark.
- **Lines** are drawn between key points to connect body parts like arms, legs, and torso.

Additionally, **hand landmarks** and **face landmarks** are drawn using the respective **MediaPipe drawing utilities**.

#### 2.2.4. Output

After processing each frame, the system displays the processed frame with the visualized landmarks. It also calculates and displays the **frames per second (FPS)** for performance tracking. The output is saved in an MP4 format for easy sharing and analysis.

### 2.3. Video Processing

- **FPS Calculation**: For each processed frame, the system calculates the FPS by comparing the time difference between consecutive frames. This information is then displayed on the video output for performance tracking.
- **Real-Time Frame Processing**: Each frame is processed one by one, detecting and visualizing landmarks as per the MediaPipe model's results.

## 3. Results

### 3.1. Performance

The performance of the video processing largely depends on the input video’s resolution, frame rate, and the complexity of the landmarks detected. For most videos with a moderate resolution (e.g., 720p), the system can process at an average of 20-30 frames per second. The FPS calculation was integrated into the video output to track performance in real time.

### 3.2. Output

The final output consists of a processed video where the detected body landmarks, hand landmarks, and face landmarks are annotated and displayed. The output video is saved in MP4 format, and the system provides a download link for users to retrieve the processed file.

### 3.3. Visualization Quality

The system successfully detects and visualizes the body landmarks, hands, and face landmarks. The lines and circles accurately reflect the positions of the landmarks, providing a clear representation of body movements. The detection works well for a variety of poses, including those with partial occlusion, though the accuracy may decrease if the subject is too far from the camera or the video quality is low.

## 4. Discussion

### 4.1. Challenges

- **Occlusion**: Landmark detection can be affected if parts of the body are blocked by other objects or body parts.
- **Real-Time Processing**: The processing speed depends on the input video’s complexity and resolution. While the system performs adequately on standard videos, it might need further optimization for real-time video streams.
- **Accuracy**: The accuracy of landmark detection can vary depending on factors such as lighting, the distance of the subject from the camera, and the video quality.

### 4.2. Future Improvements

- **Real-Time Video Stream**: Transition from video files to live stream processing to enable real-time human pose tracking.
- **Extended Landmark Features**: Implement additional gesture recognition or action classification based on the detected landmarks.
- **Performance Optimization**: Use more efficient algorithms or model fine-tuning for faster real-time processing, especially for high-resolution videos.

## 5. Conclusion

The project successfully implemented a system for detecting and visualizing body landmarks, hand landmarks, and face landmarks using **MediaPipe**'s holistic model. This approach proved to be effective for a wide range of video processing applications, with potential for use in fields such as health monitoring, animation, and gesture recognition. By leveraging **OpenCV** and **MediaPipe**, we were able to create a reliable and accurate landmark detection system with the capability of processing and visualizing video data efficiently.

## 6. References

- **MediaPipe**: https://google.github.io/mediapipe/
- **OpenCV**: https://opencv.org/
- **NumPy**: https://numpy.org/
- **Google Colab**: https://colab.research.google.com/

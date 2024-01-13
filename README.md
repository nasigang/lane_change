* This code is based on [this paper](https://www.joace.org/uploadfile/2018/1116/20181116032414410.pdf).

# Lane Change Check System

This repository contains a computer vision system that detects lanes and vehicles from video streams. The system is designed to work on pre-recorded video files and can be adapted to work with real-time video streams from webcams or other cameras.

## Description

The system implements several image processing and computer vision techniques including HLS (Hue, Lightness, Saturation) color filtering, grayscale conversion, thresholding, Gaussian blurring, edge detection with the Canny algorithm, and region of interest selection. It uses the Hough transform for line detection and the RANSAC (Random Sample Consensus) algorithm for line fitting. Additionally, it features vehicle detection using contour analysis based on the preprocessed image and lane region mask.

The main functionalities include detecting vanishing points to remove noisy lines and alerting the presence of vehicles within the lane.

## System Workflow

The workflow of the system is as follows:

1. Preprocess the input frame for line detection.
2. Detect lines using the Hough Transform.
3. Find the vanishing point to refine detected lines.
4. Fit the expected lane lines using the RANSAC algorithm.
5. Preprocess the input frame for vehicle detection.
6. Detect vehicles within the lane and issue alerts.

## Dependencies

- Python 3.x
- OpenCV (cv2)
- NumPy
- scikit-learn (for RANSACRegressor)

## Usage

Here's how to use the code to process a video file:

python from detection_system import LaneDetection, VehicleDetection
video_input_path = 'path_to_input_video.mkv' video_output_path = 'path_to_output_video.mp4'

Initialize lane and vehicle detection
lane_detector = LaneDetection() vehicle_detector = VehicleDetection()

Process video
process_video(video_input_path, video_output_path, lane_detector, vehicle_detector) ```

Replace path_to_input_video.mkv and path_to_output_video.mp4 with your input and output video file paths, respectively.

The process_video function handles frame-by-frame processing and video output.

Contributions
Contributions to this project are welcome. You can contribute by:

Reporting a bug
Discussing the current state of the code
Submitting a fix
Proposing new features
Make sure to update tests as appropriate.

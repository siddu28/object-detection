# Player Re-identification in Sports Video using YOLO and Deep SORT

## Problem Statement
The objective of this project is to track players in a single-camera sports video and maintain their unique identity using object detection and robust tracking. The goal is to assign a consistent ID to each player, even when they temporarily leave and re-enter the scene.

## Project Overview

This project integrates:

- YOLOv11 object detection (pre-trained by the company) to detect players in each frame.
- Deep SORT tracking to assign consistent player IDs using both motion and appearance information.
- OpenCV for video reading, drawing, and writing output with visualized tracks.

## Features

- Detects and tracks players frame by frame in sports videos.
- Assigns consistent IDs using Deep SORT (Kalman Filter + appearance embeddings).
- Outputs a video with bounding boxes and ID labels for each player.
- Robust to partial occlusion and re-identification after temporary disappearance.


## Steps Performed

1. Load the input video using OpenCV.
2. Load the YOLO model to detect players in each frame.
3. For each frame:
   - Detect players using YOLO (class_id = 2).
   - Format detections for Deep SORT.
   - Update Deep SORT tracker to get consistent player IDs.
   - Draw bounding boxes and labels.
   - Write the frame to the output video.
4. Save the output video with consistent player IDs.

## Output

The final output video will show bounding boxes around players with consistent IDs across frames.

## output videos

### using normal sort algorithm
https://youtu.be/UdhYkg9f7wE

### using deepsort
https://youtu.be/shDivuiQ5GQ


## Limitations
- Deep SORT can still fail in rare cases of visually identical players.

## Requirements

- Python
- OpenCV
- PyTorch
- deep_sort_realtime
- numpy
- ultralytics

## Setup Instructions

Follow the steps below to set up the project locally:

### 1. Clone the Repository

```bash
git clone https://github.com/siddu28/object-detection
```

### 2. Create Virtual environment

```bash
conda create -p venv python==3.11.5 -y
```

### 3. Activate the virtual environment

```bash
conda activate venv/
```

### 3. Install the libraries

```bash
pip install -r requirements.txt
```

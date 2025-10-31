# Virtual Fitness Trainer

This project is an AI-powered application that uses Computer Vision, Pose Estimation, and Machine Learning to accurately track exercise repetitions during workouts. The goal is to enhance fitness routines by providing real-time tracking through an easy-to-use web interface.

---

## Demo

Watch the Fitness AI Coach in action:  
[![Watch the video](https://img.youtube.com/vi/GPmDPB1bSmc/hqdefault.jpg)](https://www.youtube.com/watch?v=GPmDPB1bSmc)

---

## Table of Contents
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Overview of the WebApp](#overview-of-the-webapp)
  - [App Navigation](#app-navigation)
- [Implementation Details](#implementation-details)
  - [Exercise Classifier](#exercise-classifier)
  - [Repetition Counting](#repetition-counting)
  - [Chatbot Integration](#chatbot-integration)
- [Technologies Used](#technologies-used)
- [Warnings](#warnings)

---

## Warnings

1. The model used here, "BiLSTM Invariant," is trained without raw (x, y, z) coordinates and relies on angles and normalized distances. The best-performing hybrid model is in `train_bidirectionallstm.py`.

2. Instructional videos except `shoulder_press_form.mp4` are not included. Additional videos need to be added manually.

---

## Project Structure

- `main.py`: Runs the Streamlit app.
- `ExerciseAiTrainer.py`: Exercise-specific pose estimation logic.
- `AiTrainer_utils.py`: Utilities for image processing and distance calculations.
- `PoseModule2.py`: Body pose estimation using MediaPipe.
- `chatbot.py`: Chatbot powered by OpenAI API.
- `extract_features.py`: Extracts landmarks and angles from videos.
- `create_sequence_of_features.py`: Generates dataset sequences with features.
- `train_bidirectionallstm.py`: Training scripts for BiLSTM models.
- `requirements.txt`: Python dependencies list.
- `shoulder_press_form.mp4`: Sample exercise video.
- Pre-trained models and scalers (`*.h5`, `*.pkl`) for inference.

---

## Getting Started

### Prerequisites

- Python 3.7+ installed.
- Recommended: use a virtual environment.

### Installation

git clone https://github.com/yourusername/VirtualFitnessTrainer.git
cd VirtualFitnessTrainer
python -m venv venv

On Windows
venv\Scripts\activate

On Linux / MacOS
source venv/bin/activate
pip install -r requirements.txt


### Running the Application
streamlit run main.py

---

## Overview of the WebApp

The Virtual Fitness Trainer web app provides:

- Real-time exercise classification and repetition counting.
- Upload mode for analyzing exercise videos.
- Webcam mode for live exercise tracking.
- Auto Classify mode for automatic exercise detection.
- Chatbot feature offering fitness advice via OpenAI API.

---

## Implementation Details

### Exercise Classifier

- Uses datasets including Kaggle workout videos, synthetic avatar videos, and others.
- Model based on LSTM and BiLSTM processing body landmarks and angles.
- Optimized with accuracy, precision, recall, and F1-score metrics.

### Repetition Counting

- Manual mode: user selects exercise; counts reps via angle thresholds.
- Automatic mode: BiLSTM classifies exercises and counts reps with pose data.

### Chatbot Integration

- Uses OpenAI GPT-3.5 Turbo model via LangChain’s ConversationChain.
- Provides context-aware responses about fitness.
- Users should verify critical advice externally.

---

## Technologies Used

- MediaPipe for pose estimation.
- LSTM and BiLSTM neural networks.
- Streamlit for UI.
- Python libraries like OpenCV, TensorFlow, joblib, and more.

---

## Contact

For questions or collaboration, reach me at: [vishwabnaik16@gmail.com](vishwabnaik16@gmail.com)

Give a star ⭐ if you find this project useful!

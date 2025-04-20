# 📐 Line Pose Detection with MediaPipe

This project uses **MediaPipe** and **OpenCV** to perform real-time pose estimation and joint angle calculations from video input. It's ideal for applications like exercise form analysis, physical therapy assistance, or interactive motion-based feedback systems.

## 🚀 Features

- 📸 Real-time video processing
- 🧍 Pose detection using Google’s MediaPipe
- 📐 Joint angle calculations (elbow, shoulder, etc.)
- ✅ Angle-based pose classification
- 🖥️ Display visual feedback on processed video
- 🔁 Option to extend to rep-counting and pose correction systems

## 🛠️ Technologies Used

- Python 🐍
- OpenCV 🎥
- MediaPipe 🧠
- NumPy 📊
- Google Colab (for development and testing)

## 📁 Project Structure


## ⚙️ How It Works

1. **Capture Video Input**: From USB or webcam.
2. **Process Frames**: Convert and format image for MediaPipe.
3. **Detect Pose**: Use `mp.solutions.pose` to detect body landmarks.
4. **Calculate Angles**: Measure key joint angles from pose landmarks.
5. **Classify Pose**: Based on heuristic rules, determine pose state.
6. **Visualize**: Annotate video frames with detected pose and angles.

## 💻 Getting Started

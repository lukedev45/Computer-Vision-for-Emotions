# Smile vs Frown Detection with Arduino LCD

This project uses **OpenCV** and **MediaPipe Face Mesh** to detect whether a person is smiling or frowning via a webcam.  
The detection is based on the distance between two key facial landmarks (near the mouth corners).  
An Arduino is connected to receive serial signals and display the result on an LCD screen (or perform another action).

---

## How It Works
- Captures frames from your webcam using OpenCV.
- Uses MediaPipe Face Mesh to track facial landmarks.
- Calculates the Euclidean distance between two points around the mouth:
  - **Landmark 306 (right mouth corner)**
  - **Landmark 61 (left mouth corner)**
- If the distance is above a threshold (≥ 60 pixels) → **Smile** → sends `A` to Arduino.  
- If the distance is below the threshold (≤ 60 pixels) → **Frown** → sends `B` to Arduino.  
- The Arduino receives the serial input and displays the result on an LCD.

---

## Requirements
Install the following dependencies before running:

```bash
pip install opencv-python mediapipe pyserial

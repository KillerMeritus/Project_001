# 👁️ Third Eye: Embodied AI for the Visually Impaired

![Status](https://img.shields.io/badge/Status-Ideation%20%26%20Prototyping-blue) ![Python](https://img.shields.io/badge/Stack-Python%20%7C%20OpenCV%20%7C%20YOLOv8-green) ![Platform](https://img.shields.io/badge/Platform-Web%20%26%20Edge-orange)

> **"Most AI describes the world. Third Eye helps you grasp it."**

## 🚀 The Vision
**Third Eye** is not just another object detection app. It is a **Visual Servoing System** designed to bridge the gap between perception and action for the visually impaired. 

Instead of simply saying *"There is a bottle in front of you,"* Third Eye actively **guides the user's hand** in real-time to locate and grasp the object using spatial audio feedback (e.g., *"Move Left... Forward... Stop. Grasp now."*).

## 💡 The Problem
Visually impaired individuals often struggle with **interaction**, not just identification. Knowing a water bottle is on the table is useless if you knock it over while trying to reach for it. Current assistive AI lacks the **closed-loop feedback** needed for precise physical manipulation.

## 🛠️ The Solution: Human Visual Servoing
We are applying **Robotics Control Theory** to human assistance. By treating the human hand as a "robot end-effector," we calculate the error between the **Target Object** and the **User's Hand** in real-time and provide corrective feedback.

### Core Architecture
1.  **The Eye (Perception):** Uses **YOLOv8** to detect objects and **MediaPipe** to track the user's index finger tip.
2.  **The Brain (Logic):** Calculates the Euclidean distance and vector error between the hand and the object.
3.  **The Voice (Interface):** Converts vector error into audio commands (*"Up", "Down", "Left", "Right"*) and accepts Voice Commands (*"Find my keys"*).

## 🏗️ Tech Stack

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Object Detection** | **YOLOv8 (Nano)** | Fast, real-time detection of common objects (Bottles, Keys, Cups). |
| **Hand Tracking** | **MediaPipe Hands** | Low-latency tracking of 21 hand landmarks (Index Finger focus). |
| **Computer Vision** | **OpenCV** | Frame processing, coordinate mapping, and visualization. |
| **Backend Logic** | **Python** | Visual servoing control loop (Error calculation). |
| **Frontend/Voice** | **HTML/JS + Web Speech API** | Voice command input and user interface. |

## 🗺️ Development Roadmap (6 Weeks)

- [ ] **Phase 1: The Foundation (Current Focus)**
    - Set up Python environment & OpenCV pipeline.
    - Implement YOLOv8n for real-time object detection.
- [ ] **Phase 2: The Tracker**
    - Implement MediaPipe to track Index Finger coordinates (x, y).
    - Map normalized coordinates to pixel space.
- [ ] **Phase 3: The Logic**
    - Develop the "Control Loop": Calculate distance `D` between Hand and Object.
    - Define thresholds for "Move" vs "Grasp" states.
- [ ] **Phase 4: Integration & UX**
    - Connect Frontend Voice API to Python Backend.
    - Implement Text-to-Speech (TTS) for navigation cues.
- [ ] **Phase 5: The "Blindfold Demo"**
    - Latency optimization (<100ms).
    - Final testing in low-light conditions.

## 👥 The Team (Super 30 Batch)

* **[Member 1 Name]** - *Frontend & Voice Interface* (React/JS, Web Speech API)
* **Vivek** - *Computer Vision & Logic* (YOLO, MediaPipe, OpenCV)
* **[Member 3 Name]** - *Audio Feedback & Integration* (Python Logic, TTS)

## 🔧 Installation (Dev Setup)

*Instructions for running the prototype locally.*

```bash
# Clone the repository
git clone [https://github.com/your-username/third-eye.git](https://github.com/your-username/third-eye.git)

# Navigate to the directory
cd third-eye

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install ultralytics mediapipe opencv-python pyttsx3

# Run the vision prototype
python src/main.py
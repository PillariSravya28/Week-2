# 🚗 DriveAware: Intelligent Driver Alert System

DriveAware is an **AI-powered driver drowsiness detection system** designed to enhance road safety by monitoring the driver’s eyes in real-time using computer vision.  
When signs of drowsiness are detected, the system triggers an audible alert to wake the driver and prevent accidents.

---

## 🧠 Overview

This project uses **OpenCV**, **dlib**, and **scipy** to analyze the driver’s facial landmarks and compute the **Eye Aspect Ratio (EAR)**.  
When the EAR remains below a certain threshold for a specified time, it indicates the driver’s eyes are closed — suggesting fatigue or sleepiness.  
At that moment, the system plays an alert sound using **pygame**.

---

## ⚙️ Features

- Real-time face and eye detection using a webcam  
- EAR-based drowsiness detection algorithm  
- Automatic alert sound on detecting prolonged eye closure  
- Adjustable sensitivity and detection threshold  
- Lightweight and runs on any system with a webcam  

---

## 🧩 Technologies Used

| Component | Library/Tool |
|------------|--------------|
| Face Detection | `dlib` |
| Facial Landmarks | `shape_predictor_68_face_landmarks.dat` |
| Eye Aspect Ratio Calculation | `scipy.spatial.distance` |
| Video Processing | `OpenCV (cv2)` |
| Sound Alert | `pygame.mixer` |
| Utility Functions | `imutils` |

---

## 🗂️ Project Structure

```
DriveAware/
│
├── main.py                        # Main program file (your provided code)
├── music.wav                      # Alert sound file
├── models/
│   └── shape_predictor_68_face_landmarks.dat  # Pre-trained facial landmark model
├── README.md                      # Project documentation
└── requirements.txt               # Dependencies
```

---

## ⚡ Installation and Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/DriveAware.git
cd DriveAware
```

### 2. Install Dependencies
Make sure you have Python 3.8+ installed. Then run:
```bash
pip install opencv-python dlib imutils pygame scipy
```

### 3. Add the Model File
Download the **shape_predictor_68_face_landmarks.dat** file from:  
🔗 [Dlib Model Download Link](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

Extract it and place it in the following path:
```
models/shape_predictor_68_face_landmarks.dat
```

### 4. Add Alert Sound
Place your alert sound file as:
```
music.wav
```

---

## ▶️ How to Run

Run the script using:
```bash
python main.py
```

Press **‘q’** to quit the application.

---

## ⚖️ Parameters and Customization

| Parameter | Description | Default |
|------------|--------------|----------|
| `thresh` | Eye aspect ratio threshold | 0.25 |
| `frame_check` | Number of consecutive frames before alert | `2 × FPS` |
| `music.wav` | Sound played when drowsiness is detected | Customizable |

You can tune these parameters to make detection more or less sensitive based on lighting and camera conditions.

---

## 🧪 Working Principle

1. Capture video frames from the webcam.  
2. Detect the driver’s face and eyes using dlib’s 68 facial landmarks.  
3. Compute **Eye Aspect Ratio (EAR)** for both eyes:
   \[
   EAR = \frac{||p2 - p6|| + ||p3 - p5||}{2 \times ||p1 - p4||}
   \]
4. If EAR < threshold for a continuous duration, trigger alarm.  
5. Reset counter if eyes open again.  

---

## 🧰 Requirements File

```
opencv-python
dlib
imutils
pygame
scipy
```

Install all dependencies using:
```bash
pip install -r requirements.txt
```


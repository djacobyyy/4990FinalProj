# 🎹 ASL Gesture-Controlled Virtual Piano

This project implements a **webcam-based virtual piano** controlled using **ASL-style hand gestures**. The system uses **MediaPipe Hands** to extract hand landmarks and a **Multilayer Perceptron (MLP)** to classify gestures in real time, triggering corresponding piano notes.

---

## 🚀 Features

* Real-time hand tracking using webcam
* Gesture recognition with high accuracy (~99% validation)
* Virtual piano interface with visual feedback
* Sound playback for musical notes
* Tempo control using pinch gesture
* Stable prediction using buffering

---

## 🧠 Methodology

### 1. Hand Tracking

* MediaPipe detects **21 hand landmarks**
* Each landmark contains (x, y, z) coordinates

### 2. Feature Extraction

* Landmarks are converted into **relative coordinates from the wrist**
* This removes dependency on hand position in the frame
* Final input: **63-dimensional feature vector (21 × 3)**

### 3. Classification

* A **Multilayer Perceptron (MLP)** classifies gestures into 9 classes:

  * A, B, C, Q, V, L, Y → musical notes
  * F → rest
  * O → tempo control

---

## 🎼 Gesture Mapping

| Gesture | Action                         |
| ------- | ------------------------------ |
| A       | Play note A                    |
| B       | Play note B                    |
| C       | Play note C                    |
| V       | Play note D                    |
| Q       | Play note E                    |
| L       | Play note F                    |
| Y       | Play note G                    |
| F       | Rest (no sound)                |
| O       | Tempo control (pinch distance) |

---

## 📊 Model Performance

* **Training Samples:** ~3,500 landmark samples
* **Input Size:** 63 features
* **Classes:** 9
* **Peak Validation Accuracy:** ~99.7%

> Note: Validation data is split from only two datasets, so real-world performance may vary depending on lighting, background, and user differences.

---

## 📂 Dataset

Due to GitHub file size limitations, the dataset is hosted externally.

👉 **Download Datasets Here:**
https://www.kaggle.com/datasets/grassknoted/asl-alphabet
https://www.kaggle.com/datasets/debashishsau/aslamerican-sign-language-aplhabet-dataset

After downloading, place the dataset in the project root:

```
asl_subset/
  A/
  B/
  C/
  ...
```

---

## ⚙️ Installation

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
pip install -r requirements.txt
```

---

## ▶️ Usage

Run the demo:

```bash
python main.py
```

* Show hand gestures to the webcam
* Recognized gestures will trigger piano notes
* Press **'q'** to exit

---

## 🛠️ Technologies Used

* Python
* TensorFlow / Keras
* MediaPipe
* OpenCV
* NumPy
* Pygame

---

## ⚠️ Limitations

* Model is trained on a single dataset distribution
* Performance may drop under:

  * Different lighting conditions
  * Different users
  * Occlusions or fast motion

---

## 🔮 Future Improvements

* Add more gesture classes
* Improve generalization with diverse datasets
* Deploy on embedded/edge devices
* Add chord recognition or multi-hand support

---

## 👤 Authors
Derek Jacoby
Caleb Jala-Guinto
Jared Mocling

---

## 📜 License

This project is for educational purposes.

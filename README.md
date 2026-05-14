## 📥 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/4990FinalProj.git
cd 4990FinalProj
```
Or manually download the folder and unzip
---

### 2. Install Dependencies

```bash
pip install numpy tensorflow opencv-python mediapipe pygame matplotlib
```

---

## ▶️ Running the Project

### 🔹 Option 1: Run Real-Time Piano (Recommended)

This uses the **Landmark MLP (main model)**.

For only running the Landmark MLP demo, only run the cells with the comment #DEMO SECTION - RUN THIS SECTION

Required files:

* `ECE4990FinalProjectCode.ipynb`
* `asl_landmark_model.keras`
* `asl_landmark_classes.txt`
* `sounds/`

Run:

```bash
jupyter notebook
```

Open:

```text
ECE4990FinalProjectCode.ipynb
```

---

### 🔹 Option 2: Run Training / Experiments (MLP + MobileNetV2)

Notebooks:

* `NFinalProj.ipynb` → Landmark MLP training
* `NFinalProj_SOTA.ipynb` → MobileNetV2 (Dataset A)
* `NFinalProj_Debas.ipynb` → Landmark MLP (Dataset B)
* `NFinalProj_DebasSOTA.ipynb` → MobileNetV2 (Dataset B)

These allow you to:

* Train models
* Compare performance
* Generate accuracy graphs

---

## 📂 Dataset (Required for Training Only)

Download Dataset A:
👉 **[INSERT DATASET LINK HERE]**

Place in project folder:

```text
asl_subset/
  A/
  B/
  C/
  ...
```

---

## 🧠 Models Included

* `asl_landmark_model.keras` → Landmark MLP (main model)
* `mobilenetv2_asl_model.keras` → MobileNetV2 (baseline)

---

## 🎹 Controls

* Show hand gestures to webcam
* Gestures trigger piano notes
* Gesture **O** → tempo control (pinch fingers)
* **Press Q to quit**

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

## ⚠️ Notes

* Webcam required
* Good lighting improves accuracy
* Keep hand fully in frame
* If you are wanting to test the models against each other, DO NOT run the demo cells before running the metrics. 

---

## 📊 Summary

This project compares:

* **Landmark MLP** → fast, real-time, uses hand geometry
* **MobileNetV2** → image-based baseline

The Landmark MLP is used for the live piano system due to its speed and accuracy.

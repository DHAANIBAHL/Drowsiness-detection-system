# 🚗 Driver Drowsiness Detection System

## 📌 Overview

This project focuses on building a **driver drowsiness detection system** using deep learning and computer vision techniques. The system analyzes eye images to determine whether a driver is **alert (eyes open)** or **drowsy (eyes closed)** and can be extended into a real-time alert mechanism.

Drowsy driving is a major cause of road accidents, and this project aims to contribute to safety by detecting early signs of fatigue.

---

## 📂 Dataset

The dataset used in this project is sourced from Kaggle and contains labeled eye images.

### Structure:

```
PreparedData/
│
├── train/
│   ├── openEye/
│   └── closeEye/
│
└── test/
    ├── openEye/
    └── closeEye/
```

* **openEye** → Driver is alert
* **closeEye** → Driver is drowsy

The dataset contains thousands of images collected from multiple individuals, providing good variation for model training.

---

## ⚙️ Data Preprocessing

* Images are loaded using `ImageDataGenerator`
* Pixel values normalized from **[0, 255] → [0, 1]**
* Images resized to **224 × 224**
* Batch size: **32**
* Labels automatically assigned based on folder structure

---

## 🧠 Model

A Convolutional Neural Network (CNN) is used for binary classification:

* Convolution + ReLU layers for feature extraction
* MaxPooling layers for dimensionality reduction
* Fully connected dense layers for classification
* Sigmoid activation for binary output

---

## 🚀 How It Works

1. Images are loaded from directory structure
2. Model learns patterns distinguishing open vs closed eyes
3. During inference:

   * Input image → Model prediction
   * Output → **Open / Closed Eye**

---

## 📊 Training

Example training setup:

```python
model.fit(
    train_data,
    epochs=5,
    validation_data=test_data
)
```

---

## 🎯 Future Improvements

* 🔴 Real-time webcam integration using OpenCV
* 🔊 Alert system (alarm when drowsiness detected)
* 📈 Model optimization (Transfer Learning – MobileNet/ResNet)
* 🧪 Improve accuracy with data augmentation
* 📊 Dashboard for monitoring driver behavior

---

## 🛠️ Tech Stack

* Python
* TensorFlow / Keras
* OpenCV (for future real-time integration)
* NumPy

---

## 📁 Project Structure

```
├── dataset/
├── models/
├── notebooks/
├── src/
├── README.md
```

---

## 💡 Key Learnings

* Handling image datasets without pandas
* Using generators for memory-efficient training
* Building CNNs for classification tasks
* Understanding real-world AI applications

---

## 🤝 Contributing

Feel free to fork this repository and improve the model or add new features!

---

## 📜 License

This project is for educational and research purposes.

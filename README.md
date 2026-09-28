# DermaFusion-ML 🩺🤖

## An Ensemble Intelligence Framework Combining Deep Feature Extraction and Machine Learning for Automated Skin Disease Classification

DermaFusion-ML is an AI-powered web application developed using **Python and Django** for automated classification of skin diseases from dermoscopic images.

The system combines **EfficientNetB0 deep feature extraction** with multiple classical machine-learning classifiers and a **soft-voting ensemble** to improve classification performance on limited and imbalanced image datasets.

> **Note:** DermaFusion-ML is a research and decision-support system. It is not intended to replace professional medical diagnosis.

---

## 📌 Project Overview

Skin diseases can be difficult to identify accurately through manual image inspection, especially when large numbers of images need to be analyzed.

DermaFusion-ML provides an automated image-classification pipeline:

**Dermoscopic Image → Preprocessing → EfficientNetB0 → Feature Extraction → SMOTE → ML Classifiers → Soft Voting → Disease Prediction**

The proposed framework uses a dataset of **1,169 dermoscopic images covering eight disease categories**.

---

## 🎯 Objectives

* Develop an automated skin-disease image classification system.
* Extract deep visual features using pretrained EfficientNetB0.
* Handle class imbalance using SMOTE.
* Combine multiple machine-learning classifiers.
* Provide prediction probabilities through a Django web application.
* Display relevant disease information along with prediction results.
* Create a maintainable and scalable architecture for future improvements.

---

## 🏗️ System Architecture

```text
                  Dermoscopic Image
                         │
                         ▼
                Image Validation
                         │
                         ▼
                  224 × 224 Resize
                         │
                         ▼
                   EfficientNetB0
                 Feature Extraction
                         │
                         ▼
                1280-D Feature Vector
                         │
                         ▼
                       SMOTE
                 Class Balancing
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
         SVM       Random Forest       LDA
          │              │              │
          └──────────────┼──────────────┘
                         │
                    Naive Bayes
                         │
                         ▼
                Soft Voting Ensemble
                         │
                         ▼
                Disease Prediction
                         │
                         ▼
                 Django Web Interface
```

---

## 🧠 Algorithms Used

### 1. EfficientNetB0

A pretrained convolutional neural network is used as a deep feature extractor.

* Input size: **224 × 224**
* Feature representation: **1280 dimensions**
* Pretrained weights are used for feature extraction.

### 2. SMOTE

**Synthetic Minority Over-sampling Technique** is applied to reduce the effect of class imbalance in the extracted feature space.

### 3. Support Vector Machine

SVM is used to classify the extracted feature representations.

### 4. Random Forest

Random Forest combines multiple decision trees to perform classification.

### 5. Linear Discriminant Analysis

LDA is used as another diverse classifier in the ensemble.

### 6. Naive Bayes

Naive Bayes provides an additional probabilistic classification approach.

### 7. Soft Voting

The probability outputs of the classifiers are combined to generate the final prediction.

---

## 📊 Dataset

The project methodology uses:

* **Total images:** 1,169
* **Disease categories:** 8
* **Image type:** Dermoscopic images
* **Dataset characteristic:** Class imbalance

The dataset should be used only in accordance with its applicable research and usage permissions.

---

## 📈 Reported Results

The reported experimental results are:

| Metric            |     Result |
| ----------------- | ---------: |
| Training Accuracy | **96.40%** |
| Test Accuracy     | **82.00%** |

These values represent the reported experimental setup and should not be assumed to reproduce exactly on a different dataset, split, preprocessing pipeline, or training configuration.

---

## 💻 Technologies Used

### Backend

* Python
* Django

### Machine Learning

* TensorFlow
* Keras
* Scikit-learn
* NumPy
* Pandas
* Joblib

### Image Processing

* OpenCV
* Pillow

### Frontend

* HTML5
* CSS3
* JavaScript
* Bootstrap

### Database

* SQLite

### Development Environment

* Windows
* Python 3.11
* Visual Studio Code

---

## 📂 Project Structure

```text
DermaFusion-ML/
│
├── classifier/
│   ├── migrations/
│   ├── templates/
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── ml_service.py
│
├── skin_disease_project/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── ml_model/
│   ├── efficientnet/
│   ├── ensemble/
│   └── metadata/
│
├── training/
│   ├── feature_extraction.py
│   ├── smote_training.py
│   ├── ensemble_training.py
│   └── evaluate.py
│
├── static/
├── media/
├── templates/
├── manage.py
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/DermaFusion-ML.git
cd DermaFusion-ML
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the environment

Windows:

```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

If `requirements.txt` is not available:

```bash
pip install django tensorflow numpy pandas scikit-learn opencv-python pillow joblib
```

### 5. Apply Django migrations

```bash
python manage.py migrate
```

### 6. Start the Django server

```bash
python manage.py runserver
```

Open:

```text
http://127.0.0.1:8000/
```

---

## 🔮 Future Scope

* Grad-CAM and other visual explainability methods.
* Larger and more diverse dermoscopic datasets.
* Improved model validation and external testing.
* Model versioning and experiment tracking.
* Secure image upload and automatic deletion.
* Privacy and consent management.
* Mobile application integration.
* Cloud deployment.
* Additional deep-learning models and ensemble techniques.

---

## 🔐 Security & Privacy Considerations

The production version should include:

* File type validation.
* File size restrictions.
* Secure temporary image storage.
* Automatic deletion of uploaded images where appropriate.
* Protection against malicious file uploads.
* HTTPS/TLS.
* User consent before storing images.
* Appropriate handling of personally identifiable information.

---

## 📚 References

1. *Skin Lesion Classification in Dermoscopic Images with High Accuracy using Support Vector Machine Comparing with Random Forest Method*, IEEE ICAC3N, 2022. DOI: **10.1109/ICAC3N56670.2022.9996017**

2. *Skin Lesion Classification in Dermoscopic Images with High Accuracy Using K-Nearest Neighbor Algorithm Comparing With Random Forest Method*, IEEE ICAC3N, 2022. DOI: **10.1109/ICAC3N56670.2022.10074319**

3. *Classification of PH2 Images for Early Detection of Skin Diseases*, IEEE I2CT, 2021. DOI: **10.1109/I2CT51068.2021.9417893**

4. *Multi-Modal Framework for Skin Lesion Classification Using Deep Learning and Machine Learning Techniques*, IEEE ICMACC, 2024. DOI: **10.1109/ICMACC62921.2024.10894523**

---

## 👨‍💻 Project

**Project Name:** DermaFusion-ML
**Domain:** Artificial Intelligence / Machine Learning / Healthcare
**Framework:** Django
**Language:** Python
**Application Type:** AI-Based Web Application

---

## ⚠️ Disclaimer

DermaFusion-ML is developed for **academic and research purposes**. Predictions generated by the system should not be considered a medical diagnosis. Users should consult qualified healthcare professionals for medical evaluation and treatment decisions.

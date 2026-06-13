# Fraud SMS Detection System

## Overview

The Fraud SMS Detection System is an application designed to identify fraudulent, phishing, and spam SMS messages in real time. The solution combines an Android application with a Flask-based backend API to analyze incoming messages and classify them as either **Spam** or **Safe (Ham)** using a trained machine learning model.

---

## Features

* Real-time monitoring of incoming SMS messages
* Automatic identification of spam and fraudulent content
* Machine Learning driven message classification
* TF-IDF based feature extraction
* Multinomial Naive Bayes prediction model
* REST API integration using Flask
* Probability based risk score generation
* Android notifications for potentially suspicious messages
* SMS history management and tracking
* Backend health monitoring endpoint

---

## Technology Stack

### Frontend

* Kotlin
* Android Studio
* Android SDK
* AppCompat Libraries

### Backend

* Python
* Flask
* scikit-learn
* NLTK
* Joblib

### Machine Learning

* TF-IDF Vectorizer
* Multinomial Naive Bayes Classifier

### Storage

* Model persistence using `.joblib` files

---

## Project Architecture

```text
Incoming SMS
      │
      ▼
Android Application
      │
 REST API Request
      ▼
Flask Backend
      │
TF-IDF Vectorization
      │
Multinomial Naive Bayes Model
      ▼
Prediction Result
      │
      ▼
Android Notification
```

---

## Project Structure

```text
FraudSMSDetection/
│
├── AndroidApp/
│   ├── Activities
│   ├── BroadcastReceiver
│   ├── Notification Module
│   └── API Integration
│
├── Backend/
│   ├── app.py
│   ├── train_model.py
│   ├── sms_fraud_pipeline.joblib
│   └── requirements.txt
│
├── Dataset/
│   └── spam.csv
│
└── README.md
```

---

## API Endpoints

### Health Check

```http
GET /health
```

Response:

```json
{
  "status": "running"
}
```

### SMS Prediction

```http
POST /predict
```

Request:

```json
{
  "message": "Congratulations! You have won a free prize."
}
```

Response:

```json
{
  "prediction": "Spam",
  "probability": 0.98
}
```

---

## Dataset

The system utilizes the SMS Spam Collection Dataset, which contains labeled SMS messages categorized into:

* Spam
* Ham (Safe)

This dataset is used to train and evaluate the machine learning model for accurate message classification.

---

## Results

* Achieves high classification accuracy using TF-IDF and Naive Bayes techniques
* Provides near real time fraud and spam detection
* Lightweight backend architecture with efficient processing
* Simple and user friendly Android interface
* Effective risk assessment through probability based predictions

---

## Future Enhancements

* Support for additional platforms such as iOS
* Integration of Deep Learning based classification models
* Expansion with larger and more diverse datasets
* Improved security and privacy mechanisms
* Advanced analytics and reporting dashboard
* Cloud deployment for enhanced scalability


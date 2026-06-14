# NLP_Group_35
Enterprise Customer Support Intelligence Platform using NLP
# SupportIQ
### Intelligent NLP-Based Customer Support Ticket Classification, Routing, and Analytics System

---

## 📌 Project Overview

SupportIQ is an end-to-end Natural Language Processing (NLP) system developed for the **CCS3356 – Natural Language Processing** module at **Sri Lanka Technology Campus (SLTC)**.

The system automatically analyzes customer support tickets and performs multiple intelligent tasks including:

- Department Routing
- Ticket Type Classification
- Priority Prediction
- Sentiment Analysis
- Explainable AI Analysis
- Interactive Analytics Dashboard

The project compares traditional Machine Learning approaches with Deep Learning and Transformer-based architectures to evaluate their effectiveness in customer support automation.

---

# 🎯 Project Objectives

The primary objectives of this project are:

### 1. Ticket Classification

Automatically identify the type of customer support ticket.

### 2. Department Routing

Route tickets to the most appropriate support queue.

### 3. Priority Prediction

Predict ticket urgency levels.

### 4. Sentiment Analysis

Determine customer sentiment from ticket content.

### 5. Explainability

Provide transparent explanations for model predictions using SHAP and LIME.

### 6. Deployment

Deliver a production-style web application consisting of:

- Flask Backend API
- Streamlit Frontend Dashboard

---

# 📊 Dataset

## Dataset Name

**Multilingual Customer Support Tickets Dataset**

Source:

https://www.kaggle.com/datasets/tobiasbueck/multilingual-customer-support-tickets

---

## Dataset Description

The dataset contains multilingual customer support tickets collected from multiple support domains.

Each ticket includes:

- Subject
- Customer Message Body
- Support Response
- Ticket Type
- Support Queue
- Priority Level
- Language

---

## Dataset Schema

| Column | Description |
|----------|-------------|
| subject | Ticket title |
| body | Customer support request |
| answer | Support response |
| type | Ticket category |
| queue | Department / support queue |
| priority | Ticket priority |
| language | Ticket language |

---

## Dataset Statistics

| Metric | Value |
|----------|----------|
| Total Records | ~28,587 |
| Languages | English, German |
| Ticket Types | 4 |
| Support Queues | 10 |
| Priority Levels | 3 |

---

## Selected Dataset for Training

For model development, only English-language tickets are used.

```python
df = df[df["language"] == "en"]
```

This reduces language-related noise and improves model consistency.

---

# 🎯 Prediction Tasks

## Task 1 – Ticket Type Classification

Target Column:

```text
type
```

Classes:

```text
Incident
Request
Problem
Change
```

---

## Task 2 – Priority Prediction

Target Column:

```text
priority
```

Classes:

```text
Low
Medium
High
```

---

## Task 3 – Department Routing

Target Column:

```text
queue
```

Classes:

```text
Technical Support
Product Support
Customer Service
IT Support
Billing and Payments
Returns and Exchanges
Sales and Pre-Sales
Human Resources
General Inquiry
Service Outages and Maintenance
```

---

# 👨‍💻 Team Responsibilities

---

## Member 1
### CIT-24-01-0453

### Responsibilities

- Text Preprocessing
- TF-IDF Feature Engineering
- Logistic Regression
- BiLSTM
- Model Evaluation

### Files

```text
src/preprocessing/

cleaning.py
tokenization.py
stopwords.py
lemmatization.py
pipeline.py

src/models/member1/

logistic_regression.py
bilstm.py
```

---

## Member 2
### CIT-24-01-0023

### Responsibilities

- Word2Vec Embeddings
- SVM
- GRU
- Model Evaluation

### Files

```text
src/models/member2/

word2vec_features.py
svm_classifier.py
gru_model.py
```

---

## Member 3
### CIT-24-01-0125

### Responsibilities

- Exploratory Data Analysis
- XGBoost
- DistilBERT
- Sentiment Analysis
- Department Routing
- SHAP
- LIME
- Backend Development
- Frontend Development
- Deployment
- Final Integration

### Files

```text
src/models/member3/

xgboost_classifier.py
distilbert_classifier.py

src/sentiment/

sentiment_predictor.py

src/routing/

department_router.py
```

---

# 🏗 System Architecture

```text
Customer Ticket
       │
       ▼

Text Preprocessing
       │
       ▼

Feature Engineering
       │
 ┌─────┼─────────┐
 │     │         │
 ▼     ▼         ▼

TF-IDF Word2Vec DistilBERT

 │      │         │
 ▼      ▼         ▼

LogReg  SVM     XGBoost

BiLSTM  GRU     DistilBERT

       │
       ▼

Model Evaluation
       │
       ▼

SHAP + LIME
       │
       ▼

Flask Backend API
       │
       ▼

Streamlit Dashboard
       │
       ▼

Deployment
```

---

# 🤖 Models Implemented

## Traditional Machine Learning

### Logistic Regression

- TF-IDF Features
- Baseline Model

### Support Vector Machine (SVM)

- Word2Vec Features
- Non-linear Classification

### XGBoost

- Gradient Boosting Framework
- High-performance classification

---

## Deep Learning

### BiLSTM

- Sequential Text Learning
- Context-Aware Classification

### GRU

- Lightweight Recurrent Architecture
- Faster Training

---

## Transformer-Based Model

### DistilBERT

- Pre-trained Transformer
- State-of-the-art NLP Performance
- Transfer Learning Approach

---

# 📈 Explainable AI

The project integrates Explainable AI techniques to interpret model decisions.

---

## SHAP

Used for:

- Global Feature Importance
- Prediction Interpretation
- Model Transparency

---

## LIME

Used for:

- Local Prediction Explanation
- Individual Ticket Analysis
- Human-readable Model Insights

---

# 🧹 Data Preprocessing

The preprocessing pipeline includes:

- Lowercasing
- Special Character Removal
- Stopword Removal
- Tokenization
- Lemmatization
- Text Normalization

Combined Text Feature:

```python
df["text"] = df["subject"] + " " + df["body"]
```

---

# 📊 Evaluation Metrics

Models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

---

# 🚀 Backend

## Framework

Flask

### API Endpoints

```text
/health

/predict/type

/predict/priority

/predict/queue

/sentiment

/explain
```

---

# 🎨 Frontend

## Framework

Streamlit

### Features

- Ticket Submission
- Real-time Predictions
- Department Routing
- Sentiment Analysis
- Explainability Dashboard
- Analytics Dashboard

---

# 📂 Project Structure

```text
NLP_Group_33/

│
├── app/
│   ├── backend/
│   └── frontend/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── docs/
│
├── notebooks/
│   ├── 01_data_profiling.ipynb
│
├── reports/
│   └── eda_summary.md
│
├── presentations/
│
├── screenshots/
│   ├── preprocessing/
│   ├── models/
│   ├── frontend/
│   └── deployment/
│
├── src/
│   ├── preprocessing/
│   ├── sentiment/
│   ├── routing/
│   └── models/
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

# 🔄 Git Workflow

## Main Branch

```text
main
```

## Development Branches

```text
feature/member1-cit-24-01-0453-logreg-bilstm

feature/member2-cit-24-01-0023-svm-gru

feature/member3-cit-24-01-0125-xgboost-distilbert
```

Development is performed independently and merged into the main branch through Pull Requests.

---

# 🛠 Technology Stack

## Programming

- Python 3.12

## Data Processing

- Pandas
- NumPy

## NLP

- NLTK
- Transformers

## Machine Learning

- Scikit-Learn
- XGBoost

## Deep Learning

- TensorFlow
- Keras

## Explainability

- SHAP
- LIME

## Visualization

- Matplotlib
- Seaborn

## Backend

- Flask

## Frontend

- Streamlit

## Version Control

- Git
- GitHub

---

# 📋 Deliverables

### Source Code

Complete GitHub Repository

### Models

- Logistic Regression
- BiLSTM
- SVM
- GRU
- XGBoost
- DistilBERT

### Reports

- EDA Report
- Evaluation Report
- Final Report

### Application

- Flask Backend
- Streamlit Frontend

### Presentation

- Final Demonstration
- Viva Presentation

---

# 🎓 Academic Information

**Module:** CCS3356 – Natural Language Processing

**Institution:** Sri Lanka Technology Campus (SLTC)

**Academic Year:** 2026

---

# 👥 Authors

### Group 33

**Member 1**
CIT-24-01-0453

**Member 2**
CIT-24-01-0023

**Member 3**
CIT-24-01-0125

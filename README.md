# ✈️ Airline Passenger Satisfaction Prediction

**Team SEAborn – CIS 412 Project**
**Authors:** Ngoc Tran, Thuy Linh Luong, Long Cap, Yen Ping Choo, Xin Le Luke Goh

---

## 📘 Project Overview

This project aims to **predict airline passenger satisfaction** (Satisfied vs. Neutral/Dissatisfied) using supervised machine learning.
The analysis identifies the **key factors driving passenger experience** and helps airlines take actionable steps to improve service quality and customer retention.

---

## 🎯 Business Understanding

### Goal

To predict passenger satisfaction based on demographic, flight, and service features.

### Business Motivation

Customer satisfaction directly impacts:

* **Revenue growth**
* **Operational efficiency**
* **Competitive advantage**

### How Data Mining Helps

By analyzing passenger data, airlines can:

* Identify key satisfaction drivers
* Improve flight operations and onboard services
* Enhance personalized marketing and loyalty programs

### Expected Outcomes

* Enhanced service quality
* Increased customer retention
* Stronger market positioning

---

## 🧩 Data Understanding

### Dataset

* Source: [Kaggle – Airline Passenger Satisfaction](https://www.kaggle.com/datasets)
* Size: **~100,000 records**, **24 features**
* Feature types:
    - **Service-related:** Inflight WiFi, seat comfort, food \& drink
    - **Operational:** Flight distance, delays
    - **Customer-related:** Age, gender, travel type
    - **Booking-related:** Online check-in, ease of booking

### Data Relationships \& Quality

* Interrelated features (e.g., better service increases satisfaction)
* Minor missing values and noise handled during preprocessing

---

## 🧹 Data Preparation

### Cleaning Steps

1. Dropped unnecessary columns (`id`, `serial number`)
2. Merged `train.csv` and `test.csv` into a single DataFrame
3. Corrected data types
4. Imputed missing `Arrival Delay in Minutes` with mean values

### Preprocessing Steps

* Label encoding for categorical features
* One-hot encoding via `get\\\_dummies`
* Encoded target variable (Satisfied / Neutral-Dissatisfied)
* Split dataset: 80% training, 20% testing

---

## 🤖 Modeling

### Objective

Classify passengers as **Satisfied** or **Neutral/Dissatisfied** based on their flight experience.

### Models Tested

| Model | Strengths | Weaknesses | Test Accuracy |
|--------|------------|-------------|---------------|
| \*\*Logistic Regression\*\* | Simple, fast, interpretable | Sensitive to outliers | 0.7847 |
| \*\*Decision Tree\*\* | Handles mixed data, easy to visualize | Can overfit if unpruned | 0.9478 |
| \*\*Tuned Decision Tree (GridSearchCV)\*\* | Stable performance, optimized `max\\\_depth=11`, `max\\\_leaf\\\_nodes=49` | Slightly less interpretable | \*\*0.9408\*\* |

### Cross-Validation

* 10-fold CV with `random\\\_state=0`
* Mean accuracy: **0.948 ± 0.01**
* Very low variance → strong generalization, no overfitting

### Random Forest (Exploration)

* Evaluated for potential ensemble performance improvement (not final model)

---

## 📊 Model Evaluation

### Logistic Regression

* **Train Accuracy:** 0.7851
* **Test Accuracy:** 0.7847
* ROC and Confusion Matrix show moderate discriminative ability.

### Decision Tree (Tuned)

* **Train Accuracy:** 0.9421
* **Test Accuracy:** 0.9408
* Stable ROC and confusion matrix results
* Excellent generalization with low standard deviation across folds

---

## 🚀 Deployment Plan

### Short-Term (1–3 months)

* Predict passenger satisfaction immediately post-flight
* Send apology or discount emails for dissatisfied passengers
* Offer loyalty incentives for neutral passengers
* Improve online boarding and inflight WiFi (top-impact features)
* Establish automated customer service follow-ups

### Long-Term (3–12 months)

* Weekly analysis to identify underperforming routes
* Invest in service upgrades (WiFi, seat comfort)
* Personalize promotions for at-risk passengers
* Use satisfaction trends to guide staff training and operations

---

## ⚖️ Ethical Considerations

| Principle | Description |
|------------|--------------|
| \*\*Fairness\*\* | Regular audits to avoid bias by gender, class, or loyalty status |
| \*\*Privacy\*\* | Encrypt data; comply with GDPR, CCPA, and airline standards |
| \*\*Transparency\*\* | Use interpretable models and explain decision factors |
| \*\*Human Oversight\*\* | Predictions support — not replace — human judgment |

---

## 🧠 Key Takeaways

* **Decision Tree** model achieved **~94% accuracy** and stable cross-validation results
* **Top features** driving satisfaction: inflight WiFi, online boarding, seat comfort, and flight delays
* Airline companies can **use predictive analytics** to improve services and customer engagement proactively

---


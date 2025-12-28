# 🚚 SwiftChain Analytics – Delivery Delay Prediction

##  Project Overview
SwiftChain Analytics is a global logistics analytics company focused on improving supply chain efficiency.  
This project builds a **machine learning classification system** to predict delivery outcomes using historical logistics data.

The model classifies deliveries into three categories:
- **-1 → Late Delivery**
- **0 → On-time Delivery**
- **1 → Early Delivery**

Accurately predicting delivery delays helps businesses reduce operational costs, improve customer satisfaction, and proactively manage logistics risks.

---

##  Business Problem
Delivery delays negatively impact:
- Customer trust and satisfaction
- Operational efficiency
- Brand reputation

SwiftChain aims to **predict delivery outcomes before shipment completion**, allowing teams to:
- Flag high-risk deliveries early
- Optimize shipping modes and routes
- Improve customer communication
- Support data-driven logistics decisions

---

##  Solution Approach
A complete end-to-end machine learning pipeline was implemented, including:

- Data cleaning and validation  
- Exploratory Data Analysis (EDA)  
- Feature engineering (delivery time, pricing ratios, geography, category signals)  
- Outlier handling using IQR capping  
- Class imbalance correction using **SMOTE**  
- Model training and evaluation across multiple algorithms  
- Ensemble modeling for improved robustness  

---

##  Dataset Summary
- **Rows:** 15,549
- **Features:** 40+ numerical and categorical variables
- **Target Variable:** `label` (delivery outcome)

### Class Distribution
| Label | Meaning     | Percentage |
|------|-------------|------------|
| -1   | Late        | ~23%       |
| 0    | On-time     | ~19%       |
| 1    | Early       | ~58%       |

---

##  Feature Engineering Highlights
Key engineered features include:
- **Delivery duration metrics** (`delivery_days`, `same_day_delivery`, `long_delivery`)
- **Financial ratios** (profit margin, price ratios)
- **Geographic indicators** (top countries, order volume)
- **Product category frequency features**
- **Binary flags** for high-risk or high-impact scenarios

These features significantly improved model performance beyond raw data.

---

##  Models Trained
The following models were evaluated:

- Logistic Regression
- Random Forest
- HistGradientBoosting
- Tuned XGBoost
- Voting Ensemble (LR + RF + HGB + XGB)

Class imbalance was handled using **SMOTE**, and evaluation focused on **Accuracy and F1-Score**.

---

##  Model Performance Summary

| Model                   | Accuracy | F1 (Late) | F1 (On-time) | F1 (Early) | F1 Macro |
|------------------------|----------|-----------|--------------|------------|----------|
| **Tuned XGBoost**       | **0.60** | **0.57**  | 0.19         | **0.73**   | **0.49** |
| HistGradientBoosting   | 0.59     | 0.47      | 0.13         | 0.73       | 0.48     |
| Voting Ensemble        | 0.59     | 0.50      | 0.17         | 0.73       | 0.47     |
| Random Forest          | 0.58     | 0.37      | 0.06         | 0.72       | 0.38     |
| Logistic Regression    | 0.51     | 0.44      | 0.29         | 0.65       | 0.46     |

###  Key Insight
- The **Tuned XGBoost model** performed best overall.
- Predicting **On-time deliveries** remains challenging due to subtle class boundaries and overlapping feature patterns.
- Early and Late deliveries are more distinguishable and provide stronger predictive signals.

---

##  Feature Importance Insights
Top drivers of delivery outcomes include:
- **Shipping Mode**
- **Customer Segment**
- **Geographic Region & Country**
- **Product Category Frequency**
- **Delivery Duration Features**

These insights align strongly with real-world logistics behavior.

---

##  Business Impact
This solution enables SwiftChain Analytics to:
- Proactively identify late deliveries
- Improve logistics planning and resource allocation
- Enhance customer experience through early alerts
- Lay the foundation for real-time delivery risk prediction systems

---

##  Future Improvements
To further improve accuracy and real-world applicability:

- Integrate **external data** (weather, traffic, port congestion)
- Apply **time-aware modeling techniques**
- Use **cost-sensitive learning** to penalize late deliveries
- Improve handling of the **on-time delivery class**
- Deploy as a **real-time prediction API**
- Implement **model monitoring and retraining pipelines**

---

## Tech Stack
- **Python**
- **Pandas, NumPy**
- **Scikit-learn**
- **XGBoost**
- **Imbalanced-learn (SMOTE)**
- **Matplotlib, Seaborn**

---


---

## 👤 Author
**Keho Olamide Stella**  
Data Analyst / Machine Learning Enthusiast  

---

## 📄 License
This project is for educational and portfolio purposes.

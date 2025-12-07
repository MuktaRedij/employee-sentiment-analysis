# 📨 Employee Sentiment Analysis

This project analyzes internal employee communication using NLP and statistical modeling to evaluate sentiment, identify potential risk behavior, and support workforce engagement insights.  
It was completed as part of an internal AI practical assessment.

> ⚠ **Confidential Notice:**  
> This repository contains internal evaluation material and must **NOT be shared publicly**.  
> All content is restricted to authorized reviewers only.

---

## 📌 Project Goals

The project performs end-to-end analysis of unlabeled email communication data with the following objectives:

| Step | Objective |
|------|----------|
| 1 | Automatically label message sentiment (Positive / Negative / Neutral) |
| 2 | Perform Exploratory Data Analysis (EDA) |
| 3 | Compute monthly sentiment scores for each employee |
| 4 | Rank employees based on sentiment | 
| 5 | Identify potential flight-risk employees |
| 6 | Build and evaluate a linear regression model for trend prediction |

---

## 🧠 Methods Used

- **Natural Language Processing (NLP)**  
- **TextBlob polarity scoring**
- **Pandas time-series grouping**
- **Rolling window analysis**
- **Linear Regression (Scikit-Learn)**  
- **Matplotlib / Seaborn visualizations**

---


---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/MuktaRedij/employee-sentiment-analysis
cd employee-sentiment-analysis
```
### 2️⃣ Install required dependencies
```bash
pip install -r requirements.txt
```
### 3️⃣ Launch the notebook
```bash
jupyter notebook notebooks/Employee-Sentiment-Analysis.ipynb
```

## 🔍 Task Breakdown

---

### 🏷 1. Sentiment Labeling

Sentiment was assigned using **TextBlob polarity scores**.

| Polarity Score | Sentiment Label |
|---------------|-----------------|
| > +0.05       | Positive        |
| < −0.05       | Negative        |
| Otherwise     | Neutral         |

New columns added:

- `polarity` → numeric sentiment score  
- `sentiment` → categorical label (Positive, Neutral, Negative)

---

### 📊 2. Exploratory Data Analysis (EDA)

Key insights visualized:

- 📌 Sentiment distribution  
- 📌 Monthly sentiment trends  
- 📌 Top message-sending employees  
- (Optional) 🌥 Word clouds showing frequent terms  

All generated charts are stored in the **`visualizations/`** folder.

---

### 🧮 3. Monthly Sentiment Scoring

Scoring logic applied to each message:

| Sentiment | Score |
|----------|-------|
| Positive | +1 |
| Neutral | 0 |
| Negative | −1 |

Scores were aggregated **per employee per month** and stored for ranking and trend analysis.

---

### 🏆 4. Employee Ranking

Two ranking tables were generated **per month:**

- ⭐ Top 3 Positive Employees  
- ⚠ Top 3 Negative Employees  

Sorting logic:

> Ranked first by **sentiment score**, then alphabetically to break ties.

---

### 🚩 5. Flight-Risk Detection

An employee is flagged as a **flight risk** if:

> They sent **4 or more negative emails within any rolling 30-day window.**

A rolling calendar window was used instead of monthly boundaries to capture real behavior shifts.

Results were exported for review.

---

### 🤖 6. Predictive Modeling

A **Linear Regression model** was built using scikit-learn to predict sentiment score patterns.

Features engineered:

- Total message count  
- Average message length  
- Number of positive messages  
- Number of negative messages  
- Positive/negative sentiment ratios  

Evaluation metrics:

| Metric | Value |
|--------|-------|
| R² Score | 1.0 |
| RMSE | 5.47e-14 |

Feature coefficient interpretation is included in the notebook and visualized in the output plots.

---





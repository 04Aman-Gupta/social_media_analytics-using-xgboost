# Personalized Temporal Modeling of Social Media Addiction Risk

## Proposed Research Title
> **“Personalized Temporal Modeling of Social Media Addiction Risk Using Behavioral Change Patterns and Explainable Machine Learning”**

An interactive visual analytics system built with **Python**, **Dash**, **Plotly**, **XGBoost**, **SHAP**, **Pandas**, and **Scikit-Learn** to model longitudinal behavioral change patterns, personal usage baselines, explainable machine learning risk predictions, and early-warning alerts for student social media addiction.

---

## 💡 Key Research Novelty: Behavioral Change vs Static Behavior

Instead of evaluating users using static, single-questionnaire usage snapshots (e.g., total screen time = 6h), this system calculates **how the user's behavior is changing relative to their own personal baseline** over time:

- **$\Delta$ Screen Time** (Hours relative to personal baseline)
- **$\Delta$ Session Frequency** (App opens/day relative to baseline)
- **$\Delta$ Average Session Duration** (Minutes per session change)
- **$\Delta$ Night-Time Usage** (11 PM - 5 AM usage surge)
- **$\Delta$ Checking Frequency** (Device checks/hr surge)
- **$\Delta$ Sleep-Related Usage** (Bedtime/waking screen time change)
- **Usage Variability** (Standard deviation of screen time across weeks)

---

## 🛠️ System Architecture & Pipeline Flow

```
Social Media Usage Data (4-Week Traces)
          ↓
Behavioral Feature Extraction
          ↓
Personal Baseline Modeling (Week 1 Baseline)
          ↓
Behavioral Change Detection (Δ Features)
          ↓
XGBoost Classifier
          ↓
Addiction-Risk Score
          ↓
SHAP Explanation + Early-Warning Alert + PARI Index
```

---

## 📊 Personalized Addiction Risk Index (PARI) Innovation

$$\text{PARI} = \text{Current Risk Probability} + \text{Behavioral Change Score} + \text{Persistence Score}$$

### Risk Classifications:
- 🟢 **Stable / Low Risk** ($\text{PARI} < 35$, minimal behavioral deviation)
- 🟡 **Increasing Risk** ($35 \le \text{PARI} < 60$, moderate positive $\Delta$ escalation)
- 🟠 **Persistent High Risk** ($\text{PARI} \ge 60$, sustained elevated usage across consecutive weeks)
- 🔴 **Rapidly Increasing Risk** ($\text{PARI} \ge 70$, steep positive trajectory surge)

---

## 📁 Project Structure

```
social_media_analytics/
│
├── data/
│   ├── students_temporal_usage.csv              # Longitudinal 4-week daily trace log
│   ├── students_behavioral_change_features.csv  # Extracted baseline & Delta features
│   └── students_temporal_pari_cache.csv        # Cached PARI scores & SHAP values
│
├── src/
│   ├── data_processing.py                       # Data generation, baseline modeling, Delta feature extraction
│   ├── ml_engine.py                             # XGBoost training, SHAP TreeExplainer, & PARI calculation
│   └── visualizations.py                        # Flowchart, trajectory lines, SHAP & PARI Plotly charts
│
├── app.py                                       # Interactive Dash Web Application
├── generate_review_pdf.py                       # Viva & project review PDF generator
├── requirements.txt                             # Package dependencies
└── README.md                                    # Technical documentation
```

---

## 🚀 How to Run the Application

1. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Launch the Web Dashboard**:
   ```bash
   python app.py
   ```
   *The dashboard will launch on `http://127.0.0.1:8050/` and automatically open in your browser.*

3. **Generate Updated Review Documentation PDF**:
   ```bash
   python generate_review_pdf.py
   ```


# ChopChop User Retention Analysis

## Project Overview 
This project analyzes user behavior data from ChopChop, a meal-planning web application, to understand which product features most strongly influence 7-day user retention.
The goal is to translate behavioral event logs into actionable product insights using statistical analysis and machine learning.

## Key Business Question 
Which user behaviors and features best predict 7-day retention?
In particular, how do ChopTrack and ChopGuide—two core product features—affect user retention?

### Data Description 
The dataset consists of synthetic event-level user logs with the following key attributes:
- `event_type` (login, view_recipe, save_recipe, use_choptrack, use_chopguide)
- `used_choptrack`, `used_chopguide` (binary feature usage flags)
- `total_events` (user activity level)
- `days_since_first`
- `retained_7d` (target variable)

Data was generated to simulate realistic early-stage product usage patterns.

### Analysis Workflow
1. Data Generation & Cleaning
   Simulated user event logs and derived user-level features.
2. EDA
   Examined usage frequency, retention rates, and feature adoption patterns.
3. Feature Impact Analysis
   Conducted statistical tests to compare retained vs. non-retained users.
4. Predictive Modeling
   Built a Logistic Regression model to identify which features best predict 7-day retention.

### Key Findings
- Overall user activity (`total_events`) is the strongest predictor of retention. More engaged users are significantly more likely to return after 7 days.

- ChopTrack usage shows a positive association with retention. This suggests ChopTrack functions as a proactive engagement feature.

- ChopGuide usage is negatively associated with retention. This does not imply ChopGuide is harmful. Instead, it likely acts as a reactive support feature, used more frequently by users already at risk of churn.

Insight: Feature usage must be interpreted in context -- some features indicate engagement, while others signal user difficultly.

### Model Interpretation 
Logistic Regression coefficients were used for interpretability, allowing direct comparison of feature effects on retention probability.
The analysis emphasizes explainability over pure prediction accuracy, aligning with real-world product analytics needs.

### Business Implications
- Encourage early adoption of ChopTrack to drive proactive engagement.
- Use ChopGuide usage as a churn-risk signal, triggering targeted interventions.
- Monitor feature usage patterns rather than treating all engagement signals equally.

### Tools & Technologies
- Python(Pandas, NumPy)
- Scikit-learn
- Matplotlib/Seaborn
- Jupyter Notebook
- Git & Github

### Repo Structure
```
chopchop-yoonseo-analytics/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── 01_data_generation.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_feature_analysis.ipynb
│   └── 04_modeling.ipynb
├── report/
└── README.md
```


### Future Work 
- Time-based analysis of feature usage sequences
- Interaction effects between ChopTrack and ChopGuide
- Survival analysis for longer term retention modeling


### Author
Yoonseo Bae
Master's Student in Data Science


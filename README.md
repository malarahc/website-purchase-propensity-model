# Website Purchase Propensity Model

## Overview
This project builds a machine learning model to predict the likelihood that a website browsing session will result in a purchase. Using session-level behavioral data, the model identifies high-intent users based on engagement signals such as page views and cart activity.

The goal is to demonstrate an end-to-end data science workflow, from raw event data to actionable business insights.

## Data
The dataset contains anonymized e-commerce clickstream events, including:
- Page views
- Add to cart actions
- Purchase events
- User session identifiers

Each session is aggregated into behavioral features for modeling.
*The dataset is not included in this repository due to size constraints.*

---

## Feature Engineering
Session-level features were created by aggregating user activity:
- **Page Views**: Number of product view events per session
- **Cart Adds**: Number of add-to-cart events per session
- **Purchased (Target)**: Binary indicator of whether a session resulted in a purchase

This transformation converts raw data into a supervised learning dataset.

---

## Modeling Approach
Two classification models were trained and evaluated:

### Logistic Regression
- Used as a baseline model
- Includes feature scaling
- Provides strong interpretability
- Achieved high precision but low recall for purchase events
 
### Random Forest Classifier
- Captures non-linear relationships between engagement behaviors
- Uses class weighting to address purchase class imbalance
- Significantly improved recall, identifying a larger share of purchasing sessions

Model performance was evaluated using:
- ROC-AUC
- Confusion matrix
- Precision, Recall, and F1-score

---

## Key Results
- Purchases occur in ~5% of sessions, creating a strong class imbalance
- Logistic regression is conservative, predicting purchases only when confidence is high
- Random Forest improves buyer detection at the cost of increased false positives

---

## Feature Importance
Random Forest feature importance analysis shows:
- **Cart-related activity** is the strongest predictor of purchase intent
- **Page Views** provide additional signal but are less predictive than active engagement

This aligns with real-world behavior, where actions indicating commitment outperform passive browsing signals.


---

## Business Insights
- The model can be used to prioritize high-intent sessions for targeted marketing actions
- Decision threshold tuning allows alignment with different business goals
    - Precision-focused for costly interventions
    - Recall- focused for broader retargeting campaigns
- Behavioral engagement signals are critical drivers of conversion

---

## Future Improvements
Potential enhancements include:
- Session duration and time-based features
- Product price and category information
- User-level historical behavior
- Advanced models such as gradient boosting or neural networks

---

## Tools & Technologies
- Python
- pandas, NumPy
- scikit-learn
- matplotlib
- Jupyter Notebook
  

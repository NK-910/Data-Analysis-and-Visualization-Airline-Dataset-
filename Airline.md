# Airline Passenger Satisfaction - README

## Overview
This notebook analyzes airline passenger satisfaction using various **data visualizations and insights** extracted from passenger feedback data. The goal is to understand the key factors affecting customer satisfaction and provide actionable insights to improve airline services.

## Key Analyses & Insights

### 1. General Data Exploration
- Checked missing values and data types to ensure clean data.
- Converted categorical variables (like `satisfaction`) into numerical values for analysis.

### 2. Outlier Detection & Handling in Delays
- Analyzed **Arrival Delay** and **Departure Delay** using statistical measures:
  - **Median, Mean, Standard Deviation** were computed to understand the distribution.
  - **Interquartile Range (IQR)** was used to detect outliers.
- Outliers were identified as values **above the upper bound (Q3 + 1.5 * IQR), which was found to be 30 minutes**.
- **Approximately 14.3% of Arrival Delays and 13.7% of Departure Delays were outliers**.
- **Outliers were replaced with the median delay value (0 minutes)** to ensure data consistency and minimize skewness.

### 3. Customer Satisfaction Analysis
- **Correlation Heatmap**: Examined the relationship between **services, delays, and customer satisfaction**.
- **Violin & Box Plots**: Analyzed the **distribution of service scores across satisfaction levels**.
- **Bar Charts**: Identified which factors contribute most to customer dissatisfaction.

### 4. Impact of Flight Delays on Satisfaction
- **Scatter Plot**: Showed how increasing **departure delays impact service scores**.
- **Line Plot**: Compared how `loyal` and `disloyal` customers react to delays differently.

### 5. Service Quality & Customer Experience
- Analyzed individual services (`Inflight WiFi`, `Seat Comfort`, `Food & Drink`, etc.).
- Identified which services need improvement to boost satisfaction scores.

### 6. Predicting Customer Satisfaction (Machine Learning)
- Used **Random Forest Classifier** to predict customer satisfaction based on service ratings and delays.
- Evaluated **feature importance** to determine which services have the strongest impact.

## Key Findings

### 1. Most Influential Factors on Satisfaction:
- The highest correlation with satisfaction comes from **Inflight WiFi Service, Seat Comfort, and Inflight Entertainment**.
- **Departure & Arrival Delays have a negative impact** but are **less influential than service quality**.

### 2. Effect of Delays on Satisfaction:
- **Customers experiencing long delays tend to rate services lower**, even for unrelated services like `Food & Drink`.
- **Loyal customers tend to maintain higher satisfaction levels despite delays**, whereas disloyal customers show more variability.

### 3. Which Services Need Improvement?
- **Low-rated services**: `Baggage Handling`, `Check-in Service`, and `Ease of Online Booking` tend to have lower scores, suggesting areas for improvement.
- **Enhancing Inflight WiFi and Seat Comfort** could significantly improve overall satisfaction.

### 4. Neutral vs. Dissatisfied Passengers:
- Initially, `Neutral` and `Dissatisfied` passengers were grouped together under **Neutral or Dissatisfied**.
- To differentiate them, we calculated the **Total Service Score** (sum of all service ratings for each passenger).
- If the **Total Service Score was below 35** (half of the total possible score), the passenger was reclassified as **Dissatisfied**.
- Passengers classified as **Neutral** have a wider range of Total Service Scores, meaning they are more likely to shift to either satisfied or dissatisfied based on small changes.
- The **majority of Dissatisfied passengers have a Total Service Score below 35**, indicating a clear threshold for dissatisfaction.

### 5. Machine Learning Insights:
- The **Random Forest Model** identified `Inflight WiFi`, `Inflight Entertainment`, and `Seat Comfort` as the **strongest predictors** of satisfaction.
- The **model achieved high accuracy**, indicating that customer satisfaction can be **predicted reliably based on service factors**.

## Next Steps & Improvements
- Improve feature engineering to include **more interaction variables**.
- Explore advanced machine learning models for better predictions.
- Conduct **sentiment analysis** if textual reviews are available.

**Contributions & Suggestions are welcome!**
If you have ideas for further improving this analysis, feel free to modify the notebook and explore more insights.

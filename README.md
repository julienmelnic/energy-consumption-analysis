# Energy Consumption Analysis and Contextual Anomaly Detection

## Project Overview

This project analyzes household energy consumption data to identify usage patterns and detect anomalies using statistical and context-aware methods.

The objective is to go beyond simple threshold-based detection by incorporating temporal context into the analysis, improving the relevance of anomaly detection.

---

## Objectives

- Analyze electricity consumption patterns over time  
- Identify daily and seasonal trends  
- Detect anomalies using statistical methods  
- Improve anomaly detection using contextual features such as time, day, and season  

---

## Dataset

The dataset contains time-series data related to household electricity consumption.

Main features include:
- Global Active Power  
- Global Reactive Power  
- Voltage  
- Sub-metering values  
- Timestamp (DateTime)  

---

## Data Preparation

- Merged date and time into a unified `DateTime` column  
- Sorted data chronologically to ensure time-series consistency  
- Handled missing values using interpolation  
- Created additional time-based features:
  - Hour of day  
  - Day of week  
  - Month  
  - Season  
  - Weekend indicator  

---

## Methodology

### Baseline Anomaly Detection

A first approach uses a global statistical threshold:
- Computation of mean and standard deviation  
- Detection of anomalies using a z-score  

### Contextual Anomaly Detection

To improve accuracy, anomalies are evaluated relative to their context:
- Hour  
- Day of week  
- Season  

Each data point is compared to similar conditions using the following formula:

z-score = (value - context_mean) / context_std

This approach reduces false positives and improves interpretability.

---

## Visualization

The analysis includes:
- Time-series plots of energy consumption  
- Rolling mean smoothing to highlight long-term trends  
- Scatter plots for anomaly detection  
- Boxplots by hour and season to analyze distribution  

---

## Key Insights

### Daily Patterns

Energy consumption varies significantly throughout the day.  
Peak usage occurs during evening hours (18:00 to 22:00), corresponding to increased household activity.

---

### Seasonal Behavior

Consumption is generally higher during winter, likely due to heating needs, and lower during spring and summer.

---

### Unexpected April Anomaly

A significant anomaly is observed in April, which is unusual given that spring typically corresponds to moderate consumption levels.

This suggests a specific event or abnormal usage not explained by seasonal patterns.

---

### Importance of Context

A value that appears anomalous globally may be normal within a specific context.  
For example, high consumption in the evening may be expected, while the same value at night may be abnormal.

Contextual anomaly detection improves accuracy by accounting for these variations.

---

## Limitations

- Global statistical methods can generate false positives  
- Some detected anomalies may correspond to legitimate high consumption  
- Contextual grouping may be sensitive to small sample sizes  

---

## Conclusion

This project highlights the importance of contextual analysis in time-series anomaly detection.

By incorporating temporal features such as hour, day, and season, it is possible to improve the relevance and accuracy of anomaly detection.

Such approaches can be applied to real-world energy monitoring systems to better understand consumption behavior and identify abnormal patterns.

---

## Technologies Used

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  

---

## Project Structure

energy-consumption-analysis/
│── data/  
│── notebook.ipynb  
│── README.md  
│── requirements.txt  

---

## Author

Julien Melnic
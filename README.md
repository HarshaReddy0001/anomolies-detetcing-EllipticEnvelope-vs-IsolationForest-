# Project Title: Temperature Anomaly Detection for Device Failure Prediction

## Introduction
This project analyzes temperature time series data to detect anomalies that may indicate potential device failure. The goal is to identify unusual temperature patterns that could serve as early warning signs of device malfunction, enabling proactive maintenance and reducing downtime.

## Dataset
The data used in this project is a time series dataset containing temperature readings. It includes a timestamp and a temperature value. The dataset was obtained from [mention the source if possible, otherwise state that it's a provided dataset].

## Problem Statement
The primary problem addressed is the identification of abnormal temperature readings within the time series data. These anomalies are hypothesized to be indicators of potential device failure. The project aims to categorize these anomalies based on time of day and day of the week to understand if certain periods are more prone to unusual temperature fluctuations.

## Methodology
The approach involves several steps:
1. **Data Loading and Exploration:** Loading the temperature data and examining its structure and characteristics.
2. **Time Series Visualization:** Plotting the temperature data over time to observe trends and patterns.
3. **Feature Engineering:** Creating new features to categorize data by time of day (Day/Night) and day of the week (Weekday/Weekend).
4. **Anomaly Detection:** Applying two different anomaly detection algorithms:
   - **Elliptic Envelope:** Assuming the normal data follows a Gaussian distribution.
   - **Isolation Forest:** An ensemble method that isolates anomalies based on random partitioning.
5. **Visualization and Analysis of Anomaly:** Visualizing the detected anomalies for each category and comparing the results from both algorithms.
6. **Counting Anomalies:** Quantifying the number of anomalies detected in each category.

## Results
Based on the analysis of the temperature time series data:

- The time series plot shows the temperature fluctuations over time.
- Categorizing the data by "Weekday Day", "Weekday Night", "Weekend Day", and "Weekend Night" allowed for analyzing anomaly detection within these specific periods.
- The Elliptic Envelope algorithm, assuming a Gaussian distribution, detected the following number of anomalies in each category:
    - Weekday Night: 132
    - Weekday Day: 132
    - Weekend Night: 51
    - Weekend Day: 51
- The Isolation Forest algorithm, which is less sensitive to assumptions about data distribution, detected a consistent number of anomalies across all categories (51), which could indicate that it identified anomalies based on a more general pattern across the entire dataset, or that the 5% contamination parameter resulted in a fixed number of anomalies being identified per category due to the way the data was split.
- The visualizations of anomalies for each category show the distribution of normal and anomalous temperature values.

## Conclusion
Comparing the results of the two anomaly detection algorithms:

- Elliptic Envelope identified more anomalies in the "Weekday Day" and "Weekday Night" categories compared to "Weekend Day" and "Weekend Night". This might suggest that temperature fluctuations are more varied during weekdays.
- Isolation Forest detected a consistent number of anomalies across all categories (51), which could indicate that it identified anomalies based on a more general pattern across the entire dataset, or that the 5% contamination parameter resulted in a fixed number of anomalies being identified per category due to the way the data was split.
- From the visual inspection of the histograms, both algorithms seem to perform reasonably well in detecting anomalies. However, Isolation Forest might be more robust to the specific distribution of the data within each category.
- The identified anomalies can serve as potential indicators of device stress or impending failure, which can inform a predictive maintenance strategy.
- Future steps could involve investigating the nature of the detected anomalies further, exploring other anomaly detection techniques, or incorporating additional sensor data for a more comprehensive analysis.

## Installation/Usage
To run this notebook:
1. Clone the repository to your local machine or open it directly in Google Colab.
2. Ensure you have the necessary libraries installed (pandas, matplotlib, scikit-learn). You can install them using pip:

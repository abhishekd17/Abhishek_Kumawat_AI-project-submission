# Employee Sentiment Analysis

This project performs **Employee Sentiment Analysis** on internal communication data using NLP and data science techniques. It classifies messages by sentiment, tracks trends over time, identifies top positive/negative employees, detects flight-risk employees, and predicts future sentiment trends.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Tools & Libraries](#tools--libraries)
- [Implementation Steps](#implementation-steps)
- [How to Run](#how-to-run)
- [Outputs & Visualizations](#outputs--visualizations)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Project Overview

This project analyzes employee message sentiment using the `TextBlob` library. It processes messages with columns: `subject`, `body`, `time`, and `from` (employee). 

Key features:
- Sentiment classification (Positive, Negative, Neutral)
- Sentiment distribution visualization
- Monthly sentiment trend analysis
- Employee scoring and ranking by sentiment
- Detection of flight-risk employees (based on negative message frequency)
- Sentiment trend prediction via Linear Regression
- Export of comprehensive Excel report and visual assets

---

## Dataset

The dataset (`test.csv`) should contain these columns:
- `subject`: Message subject
- `body`: Message text content
- `time`: Timestamp of the message (ISO format preferred)
- `from`: Employee identifier (name or ID)

---

## Tools & Libraries

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- textblob
- scikit-learn
- Jupyter Notebook or Google Colab

---

## Implementation Steps

1. **Data Loading and Cleaning**
   - Load CSV using pandas.
   - Convert `time` column to datetime format.
   - Remove invalid timestamps.

2. **Sentiment Classification**
   - Use TextBlob to calculate polarity scores.
   - Classify messages as Positive (>0.1), Negative (<-0.1), or Neutral.

3. **Sentiment Visualization**
   - Plot overall sentiment distribution.
   - Plot monthly sentiment trends (stacked bar chart).

4. **Employee Scoring**
   - Assign scores: +1 (Positive), 0 (Neutral), -1 (Negative).
   - Aggregate monthly scores by employee.
   - Plot score distribution.

5. **Identify Top Employees**
   - Determine top 3 positive and negative employees each month.

6. **Flight Risk Detection**
   - Flag employees with 4+ negative messages within 30 days.
   - Visualize negative message timelines for flagged employees.

7. **Trend Prediction**
   - Train linear regression model on monthly sentiment scores.
   - Predict and visualize sentiment trend.

8. **Export Report**
   - Save cleaned data, monthly sentiment, scores, and top employees into an Excel report.
   - Save all plots as PNG images in a `/visuals` folder.

---

## How to Run

### Option 1: Run on Google Colab

1. Upload your `test.csv` dataset to Google Drive or directly to Colab.
2. Open [this Colab notebook](#) (create your own or upload your code).
3. Run the notebook cells step-by-step to execute the full pipeline.
4. Visualizations will display inline.
5. Download exported Excel report and images from the Colab environment.

### Option 2: Run Locally

1. Clone this repository.
2. Ensure Python 3.x is installed.
3. Install dependencies:

   ```bash
   pip install pandas numpy matplotlib seaborn textblob scikit-learn
   python -m textblob.download_corpora

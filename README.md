# 📊 Elevating Education with Sentiment Analysis and Power BI Insight

## 📚 Table of Contents
- [📌 Project Overview](#-project-overview)
- [🧠 Problem Statement](#-problem-statement)
- [🎯 Objectives](#-objectives)
- [🧰 Tech Stack](#-tech-stack)
- [🏗️ Methodology](#-methodology)
- [🔧 System Architecture](#-system-architecture)
- [🚀 How to Run](#-how-to-run)
- [👨‍💻 Author](#-author)
- [📄 License](#-license)

## 📌 Project Overview

In an era where data drives decisions, the educational sector often lacks a structured approach to analyze and act on student feedback. This project bridges that gap by leveraging **Sentiment Analysis** and **Power BI** to extract insights from student reviews, enhancing institutional strategies and improving learning experiences.

> "Understanding student emotions isn't optional—it's essential."

## 🧠 Problem Statement

Educational institutions lack a structured pipeline to collect, analyze, and act on student feedback in real time. This hinders content optimization and data-driven decision-making.

> 🔍 **Goal**: Use NLP and visualization tools to generate actionable insights that support personalized learning and improve course delivery.

## 🎯 Objectives

- Automate data extraction from Google Maps college reviews using Selenium.
- Preprocess text using NLTK (tokenization, stopword removal, stemming).
- Classify feedback sentiment using ML models (Logistic Regression, Naive Bayes, SVM).
- Visualize trends using **Power BI dashboards** (loaded from exported CSV).
- Suggest improvements to academic content and teaching methods based on negative review analysis.

## 🧰 Tech Stack

### ⚙️ Tools & Languages

- **Python** – Core programming
- **Jupyter Notebook** – Prototyping and experimentation
- **Power BI** – Interactive dashboards and data visualization
- **Selenium** – Web scraping (Google Maps reviews)
- **NLTK, TextBlob** – Natural Language Processing
- **scikit-learn** – ML models and evaluation
- **pandas, numpy** – Data handling
- **matplotlib, seaborn** – Charts and visualizations

## 🏗️ Methodology

1. **Web Scraping** – Selenium scrapes Google Maps reviews for a college (author, rating, text, date).
2. **Data Preprocessing** – Tokenization, stopword removal, and stemming using NLTK.
3. **Sentiment Labeling** – Star ratings used as ground truth (1-2=negative, 3=neutral, 4-5=positive); TextBlob as fallback.
4. **Feature Extraction** – TF-IDF vectorization with n-grams (1,3).
5. **Model Training** – Logistic Regression, Naive Bayes, SVM with GridSearchCV hyperparameter tuning.
6. **Evaluation** – Confusion Matrix, ROC Curve, classification report.
7. **Visualization** – Sentiment distribution, trend over time, improvement areas chart.
8. **Power BI Export** – Processed data exported to `sentiment_for_powerbi.csv` for dashboard building.
9. **Improvement Suggestions** – Top complaint keywords from negative reviews mapped to actionable categories.

## 🔧 System Architecture

```
[Input Layer]
      ↓
Google Maps Scraping (Selenium)
      ↓
Data Cleaning & Preprocessing (NLTK)
      ↓
Sentiment Labeling (Star Ratings / TextBlob)
      ↓
Feature Extraction (TF-IDF)
      ↓
ML Model Training & Evaluation (scikit-learn)
      ↓
Visualization (matplotlib / seaborn)
      ↓
Export → Power BI Dashboards + Improvement Suggestions
```

## 🚀 How to Run

1. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

2. **Install ChromeDriver** (required for scraping)
   - Download from [https://chromedriver.chromium.org/downloads](https://chromedriver.chromium.org/downloads)
   - Version must match your installed Chrome (`chrome://version`)
   - Add to system PATH

3. **Run the notebook**
   ```bash
   jupyter notebook sentiment_analysis.ipynb
   ```
   - **Option 1 — Scrape live data**: In Cell 2, uncomment Option 1 and set your college's Google Maps URL
   - **Option 2 — Use existing CSV**: In Cell 2, set `CSV_PATH` to your CSV file path (must have a `text` column; `rating` column optional but recommended)
   - NLTK data is downloaded automatically in Cell 1

4. **Load into Power BI**
   - Open Power BI Desktop
   - Import `sentiment_for_powerbi.csv` (generated after running the notebook)
   - Build dashboards: sentiment trend over time, rating distribution, complaint areas

## 👨‍💻 Author
**Aaryan Puri**
[LinkedIn](https://www.linkedin.com/in/aaryan-puri-04923a228/) • [GitHub](https://github.com/AaryanPuri)

## 📄 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

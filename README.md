# 📊 Instagram Reach Analysis using Python

## 🚀 Project Overview

This project explores what drives Instagram post visibility using real post data. From analyzing where impressions come from to predicting reach using engagement metrics, the goal is to extract insights and build a simple yet effective model that predicts a post's potential performance.

---

## 📂 Dataset Description

The dataset contains detailed metrics per post, including:

- **Impressions from Sources:**
  - From Home 📱
  - From Hashtags 🏷️
  - From Explore 🔍
  - From Other 💬

- **Content Info:**
  - Caption 📝
  - Hashtags #

- **Engagement Metrics:**
  - Likes ❤️
  - Saves 🔖
  - Shares 📤
  - Comments 💬

- **Reach:** Number of unique users who saw the post

**Location**: `data/Instagram data.csv`

---

## 🔍 Exploratory Data Analysis (EDA)

### ✅ Data Cleaning
- Removed missing values (`NaN`)
- Verified data types for all columns
- Checked dataset consistency

### 📈 Impressions Distribution
Used **Seaborn** to plot the distribution of impressions from:
- Home
- Hashtags
- Explore
- Other

Helped identify the most impactful sources.

### 🥧 Source Contribution (Pie Chart)
Created a **Plotly** pie chart to show proportion of impressions from:
- 📱 Home (followers)
- 🏷️ Hashtags (discoverability via tags)
- 🔍 Explore (algorithmic recommendations)
- 💬 Other (shares, DMs, profile visits)

### ☁️ Word Clouds
Generated word clouds for:
- **Captions**: Common words and phrases
- **Hashtags**: Frequently used tags

Helped identify popular language trends among posts.

---

## 📊 Correlation Analysis

Used `df.corr()` and a heatmap to study correlation between features and **Reach**.

### 📌 Strong Positive Correlations:
- Impressions
- Likes
- Saves
- Shares

These metrics are **key predictors** of post performance.

---

## 🧠 Predictive Modeling

### 🎯 Goal:
Predict **Reach** using engagement and impression data.

### 🔧 Model Used:
**Passive Aggressive Regressor** from `scikit-learn`  
Chosen for its efficiency and suitability for regression tasks on social data.

### 🧪 Process:
1. **Feature Selection:**  
   - Likes, Saves, Shares, Comments, Impressions
2. **Train-Test Split:**
   - 80% training / 20% testing
3. **Training & Evaluation:**
   - Trained the model and printed performance score using `.score()`

# 📊 Predicting Instagram Reach with Engagement Metrics

This project explores how user interactions like **likes**, **saves**, **shares**, and **comments** influence Instagram **reach**. Using exploratory data analysis and machine learning, we uncover actionable insights and build a predictive model to estimate post reach.

---

## 📌 Key Insights

- **Hashtags** and **Home feed** are primary drivers of impressions.
- Posts with high **likes**, **saves**, and **shares** tend to achieve greater **reach**.
- **Word clouds** reveal common patterns in captions and hashtags.
- A basic **machine learning model** can effectively predict reach based on engagement data.

---

## 🧠 Machine Learning Model

```python
from sklearn.linear_model import PassiveAggressiveRegressor
from sklearn.model_selection import train_test_split

features = df[['Likes', 'Saves', 'Shares', 'Comments', 'Impressions']]
target = df['Reach']

X_train, X_test, y_train, y_test = train_test_split(features, target, test_size=0.2, random_state=42)

model = PassiveAggressiveRegressor()
model.fit(X_train, y_train)

score = model.score(X_test, y_test)
print("Model R^2 Score:", score)

## 🛠 Tools & Libraries Used

- `pandas`, `numpy` – Data manipulation  
- `matplotlib`, `seaborn`, `plotly` – Data visualization  
- `wordcloud` – Text analysis  
- `scikit-learn` – Machine learning modeling  

---

## 🧾 Conclusion

This project highlights how **data-driven insights** can uncover the mechanics of Instagram reach. Through exploratory analysis and machine learning, we discovered that:

- Impressions from **hashtags** and the **home feed** are major contributors to visibility.
- **Engagement metrics**—especially likes, saves, and shares—strongly influence how widely a post is seen.
- **Captions and hashtags** show language trends that might resonate with the audience.
- Even a basic **regression model** can predict reach effectively using interaction data.

While this is a foundational analysis, it opens the door to deeper exploration—such as:

- Incorporating **sentiment analysis** of captions  
- Exploring **optimal posting times**  
- Comparing **content types** and formats  

By understanding what drives performance, creators and marketers can better tailor their content for **maximum impact**.

> **Data meets creativity.** And in that intersection, visibility thrives. 🚀

---

## 👋 Let's Connect

If you're into **data**, **social media analytics**, or **influencer strategy**, feel free to connect and collaborate!

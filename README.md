
# 🎵 Song Popularity Analytics

**Objective:** Analyze and predict the popularity of songs using audio features and statistical modeling.

---

## 📁 Dataset Overview

- **Size:** ~10,000 songs (1950–present)
- **Format:** Excel file with numeric audio features and metadata (genre, year, etc.)
- **Target Variable:** `Popularity` (converted to binary — `Popular` if score > 50)

---

## 🔍 Exploratory & Statistical Analysis

- Visualized audio features across popularity classes using **Seaborn** and **Matplotlib**
- Conducted **T-Tests** to compare mean values between popular and non-popular songs for:
  - **Danceability**, **Loudness**, **Valence**, **Speechiness**, **Acousticness**, **Instrumentalness**, **Liveness**
  - All above features showed statistically significant differences
  - **Tempo** and **Energy** did not show significant difference
- For **Genre** (a multi-class feature), applied **ANOVA** instead of repeated t-tests to avoid multiple comparison errors
  - Found that songs labeled with the **Pop** genre have significantly higher mean popularity
  - Bar charts confirmed that **Pop** genre songs are more likely to become popular

---

## ⚙️ Data Processing & Modeling

- **Preprocessing:**
  - Converted `Popularity` to binary (`0` for Not Popular, `1` for Popular)
  - Standardized numerical features using `StandardScaler`
  - Handled missing values and cleaned categorical columns

- **Train-Test Split:** 80:20 using `train_test_split` with stratification

- **Models Trained:**
  - `Linear Regression` to analyze impact of continuous features
  - `Logistic Regression` for binary classification

- **Evaluation Metrics:**
  - **Accuracy:** 68.70%
  - **Confusion Matrix**: Used to visualize true vs predicted classes
  - **Classification Report:** Precision, Recall, F1-score for both classes
  - **AUC-ROC Score:** Evaluated model’s ability to distinguish between popular and non-popular songs

---

## 🔄 Clustering & PCA

- Used **K-Means Clustering** to group songs into clusters based on audio similarity
  - Helped identify natural groupings like acoustic, energetic, or speech-heavy songs
- Applied **PCA** for dimensionality reduction and visualization of clusters

---

## 📊 Key Insights

- **Danceability**, **Loudness**, **Valence**, **Acousticness**, and **Speechiness** are strong indicators of popularity
- **Pop genre** songs show significantly higher mean popularity than other genres
- Logistic Regression provided moderate predictive accuracy (68.70%), while statistical and clustering techniques added deeper interpretability

---

## 🛠 Tools & Technologies

- **Language:** Python  
- **Libraries:**  
  - `pandas`, `numpy` – data handling  
  - `seaborn`, `matplotlib` – visualization  
  - `scikit-learn` – modeling, evaluation, clustering  
  - `scipy`, `statsmodels` – statistical tests

---

##  Conclusion

This project combines statistical analysis and machine learning to uncover the drivers of song popularity. Danceability and Pop genre emerged as the most influential factors in determining whether a song is likely to become a hit.

---

*Author: [Manya]*  
*Project Duration: October 2024 – December 2024*

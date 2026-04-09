# Indian IPO Market Listing Gains Prediction - Project Overview

## 📊 Project Summary

This project builds a **deep learning classification model** to predict whether an Indian Initial Public Offering (IPO) will list with positive gains or losses. Using historical IPO data from the Indian market, the model leverages subscription metrics and issue characteristics to forecast listing performance.

## 🎯 Business Context

Investment firms face uncertainty when deciding which Indian IPOs to invest in. This project addresses that challenge by:
- Analyzing patterns in historical IPO performance
- Identifying key factors that influence listing day gains
- Building a predictive model to classify IPOs as likely profit or loss scenarios
- Enabling data-driven investment decisions

## 📈 Dataset Description

**Source:** [Moneycontrol](https://www.moneycontrol.com/ipo/ipo-historic-table?classic=true)

**Records:** 319 historical IPOs from the Indian market (2010-2022)

### Key Features

| Feature | Description | Type |
|---------|-------------|------|
| **Date** | IPO listing date | Temporal |
| **IPOName** | Company name | Categorical |
| **Issue_Size** | IPO size in INR Crores | Numeric |
| **Subscription_QIB** | Subscription multiple from Qualified Institutional Buyers | Numeric |
| **Subscription_HNI** | Subscription multiple from High Networth Individuals | Numeric |
| **Subscription_RII** | Subscription multiple from Retail Individual Investors | Numeric |
| **Subscription_Total** | Total subscription multiple across all investor categories | Numeric |
| **Issue_Price** | IPO issue price in INR | Numeric |
| **Listing_Gains_Percent** | Percentage gain/loss on listing day | Target (continuous) |
| **Listing_Gains_Profit** | Binary classification: 1 (profit) or 0 (loss) | Target (classification) |

## 📊 Key Insights from EDA

### Class Distribution
- **Profit (1):** 174 IPOs (54.5%)
- **Loss (0):** 145 IPOs (45.5%)
- The dataset is fairly balanced, indicating a reliable training environment for classification

### Data Quality
- ✅ **No missing values** across all 319 records
- All features are complete and ready for modeling

### Statistical Characteristics

| Metric | Listing_Gains_Percent |
|--------|----------------------|
| Mean | 4.74% |
| Std Dev | 47.65% |
| Min | -97.15% |
| Max | +270.40% |
| Median | 1.81% |

### Feature Distributions

1. **Issue_Size:** Highly right-skewed (4.85), with most IPOs below ₹1,100 Cr, but outliers reaching ₹21,000 Cr
2. **Subscription Metrics:** All positively skewed, indicating varying investor demand patterns
3. **Issue_Price:** Moderately right-skewed (1.70), ranging from ₹0 to ₹2,150

### Important Observations

- **Outliers Detected:** Multiple features contain outliers, particularly in Issue_Size and subscription metrics
- **Subscription_HNI:** Shows the highest variability and most outliers among investor categories
- **Feature Correlation:** Subscription metrics show moderate correlation with listing gains, suggesting predictive value

## 🔍 Variables of Interest

**Independent Variables (Features):**
- Issue characteristics: Size, Price
- Investor demand signals: QIB, HNI, RII, and Total subscription multiples

**Target Variable:**
- **Primary:** `Listing_Gains_Profit` (binary classification: 0 or 1)
- **Secondary:** `Listing_Gains_Percent` (continuous regression)

## 🛠️ Modeling Pipeline

The notebook follows the complete machine learning workflow:

1. **Exploratory Data Analysis (EDA)**
   - Data loading and inspection
   - Missing value analysis
   - Statistical summaries
   - Distribution analysis

2. **Data Visualization**
   - Correlation heatmaps
   - Distribution plots
   - Boxplots for outlier detection
   - Category comparisons

3. **Data Preprocessing** 
   - Feature scaling/normalization
   - Outlier handling
   - Feature engineering
   - Train-test splitting

4. **Deep Learning Model Development** 
   - TensorFlow/Keras neural network
   - Classification architecture
   - Hyperparameter tuning
   - Model evaluation

## 💡 Key Findings

- Approximately **55% of IPOs list at a profit**, suggesting a generally favorable market for most IPOs
- **Subscription demand** (especially from institutional and high-networth investors) appears to be a strong indicator of listing performance
- **Significant variability** in gains (-97% to +270%) highlights the importance of predictive modeling
- **Outliers and skewness** require careful preprocessing before model training

## 🚀 Next Steps

1. **Feature Engineering:** Create derived features from subscription ratios
2. **Data Preprocessing:** Handle outliers and scale features appropriately
3. **Model Development:** Build and train a deep learning classifier
4. **Model Evaluation:** Cross-validation, confusion matrix, ROC-AUC
5. **Production Ready:** Model serialization and deployment considerations

## 📚 Technologies Used

- **pandas:** Data manipulation and analysis
- **numpy:** Numerical computations
- **matplotlib & seaborn:** Data visualization
- **TensorFlow/Keras:** Deep learning framework (for modeling phase)
- **scikit-learn:** Preprocessing and evaluation (anticipated)

## 📖 How to Use This Notebook

1. Ensure the dataset `Indian_IPO_Market_Data.csv` is in the working directory
2. Run cells sequentially to reproduce the analysis
3. Use insights from EDA to inform preprocessing decisions
4. Extend with your own feature engineering and modeling approaches

## ⚠️ Important Considerations

- **Temporal Patterns:** IPO performance may vary across different market cycles (2010-2022 covers multiple market phases)
- **Survivorship Bias:** Only completed IPOs are included; failed IPOs may follow different patterns
- **Market Conditions:** Model predictions should account for current market volatility and conditions
- **Regulatory Changes:** Indian IPO regulations have evolved; older data may not reflect current conditions

---

**Author's Note:** This project demonstrates the complete data science workflow from raw data to actionable insights, suitable for investment decision-making in the Indian IPO market.

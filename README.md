# Customer-Churn-Analysis-and-Behavioral-Segmentation [E-COMMERCE]

## Project Overview

This project analyzes customer churn behavior for an e-commerce business. The goal is to identify key churn drivers, build a supervised machine learning model to predict churn, segment churned customers using unsupervised learning, and provide actionable business recommendations to improve customer retention.

## Business Objectives

- Understand the characteristics of churned customers.
- Identify behavioral and demographic factors related to churn.
- Build a machine learning model to predict whether a customer is likely to churn.
- Segment churned customers into meaningful groups for targeted marketing actions.
- Recommend retention strategies based on data-driven insights.

## Dataset

The dataset contains customer-level information from an e-commerce platform, including customer behavior, engagement, satisfaction, complaints, payment preferences, order categories, and churn status.

Key types of features include:

- Customer tenure
- App usage behavior
- Order frequency
- Coupon usage
- Cashback amount
- Satisfaction score
- Complaint status
- Preferred login device
- Preferred payment mode
- Preferred order category
- Marital status
- Churn label

## Project Workflow

### 1. Data Understanding and Cleaning

- Load the dataset.
- Inspect data shape, data types, duplicate records, and missing values.
- Drop records with missing `Tenure` values.
- Fill missing numerical values using the median.
- Remove unnecessary columns such as customer identifiers and selected low-priority fields.

### 2. Exploratory Data Analysis

- Analyze distributions of numerical features using histograms.
- Detect outliers using boxplots.
- Review feature correlations using a heatmap.
- Compare churn distribution across categorical variables.
- Generate initial business insights from customer behavior patterns.

### 3. Feature Engineering and Preprocessing

- Check multicollinearity using Variance Inflation Factor (VIF).
- Encode categorical variables using one-hot encoding.
- Split the dataset into training and testing sets.
- Normalize selected numerical features using `MinMaxScaler`.

### 4. Supervised Learning: Churn Prediction

- Define features and target variable.
- Train a Random Forest classifier.
- Tune hyperparameters using `GridSearchCV`.
- Evaluate the model using balanced accuracy, classification report, and confusion matrix.

### 5. Model Interpretation

- Extract feature importance from the Random Forest model.
- Visualize the top features contributing to churn prediction.
- Use model insights to understand important churn drivers.

### 6. Unsupervised Learning: Customer Segmentation

- Filter only churned customers.
- Select relevant features for clustering.
- Apply PCA for dimensionality reduction.
- Use the Elbow Method to determine the number of clusters.
- Apply K-Means clustering with `k = 3`.

### 7. Cluster Profiling

- Analyze customer count and percentage by cluster.
- Compare average numerical values across clusters.
- Visualize behavioral differences using boxplots.
- Review one-hot encoded feature proportions by cluster.
- Build a supporting classifier to explain cluster assignment patterns.

### 8. Business Insights and Recommendations

The churned customers are segmented into three groups:

#### Cluster 0: At-Risk Newcomers

Characteristics:

- Low tenure
- Low order count
- High number of days since last order
- Low app engagement

Recommended actions:

- Improve onboarding experience.
- Provide welcome offers or early retention incentives.
- Personalize app content to increase early engagement.

#### Cluster 1: High-Risk Churners

Characteristics:

- High-risk churn behavior
- Declining engagement
- Potentially lower satisfaction or more complaints

Recommended actions:

- Run re-engagement campaigns.
- Send special vouchers, email reminders, and push notifications.
- Improve customer service and complaint resolution.
- Set up early-warning triggers for declining activity.

#### Cluster 2: Deal-Driven Potentials

Characteristics:

- Medium tenure
- Moderate order count
- Responsive to coupons and cashback
- Unstable engagement behavior

Recommended actions:

- Offer personalized promotions.
- Use vouchers and cashback strategically.
- Encourage cross-selling.
- Build loyalty programs to increase long-term retention.

## Tools and Libraries

This project uses the following Python libraries:

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
gdown
```

## Machine Learning Methods

### Supervised Learning

Model used:

- Random Forest Classifier

Main techniques:

- Train-test split
- Feature scaling
- Hyperparameter tuning with GridSearchCV
- Balanced accuracy evaluation
- Feature importance analysis

### Unsupervised Learning

Methods used:

- Principal Component Analysis (PCA)
- K-Means clustering
- Elbow Method
- Silhouette Score
- Cluster profiling

## Repository Structure

```text
.
├── Customer_Churn_Analysis_and_Behavioral_Segmentation.ipynb
└── README.md
```


This notebook separates each workflow step and sub-step into individual code cells, making it easier to follow and run in Google Colab or Jupyter Notebook.

## How to Run

1. Open the notebook file:

```text
Customer_Churn_Analysis_and_Behavioral_Segmentation.ipynb
```

2. Run all cells from top to bottom.

3. Make sure the required libraries are installed. If running on Google Colab, most libraries are pre-installed. The notebook also installs `gdown` if needed.

4. The dataset is downloaded automatically using Google Drive file ID through `gdown`.

## Key Outputs

- Cleaned and preprocessed dataset
- EDA visualizations
- Churn prediction model
- Model evaluation metrics
- Feature importance chart
- PCA-based clustering results
- Cluster profiles
- Business recommendations for customer retention

## Conclusion

This project provides an end-to-end churn analytics workflow, combining exploratory data analysis, supervised machine learning, unsupervised customer segmentation, and business recommendation development. The results can help an e-commerce company identify high-risk customers earlier and design targeted retention strategies for different churned customer segments.

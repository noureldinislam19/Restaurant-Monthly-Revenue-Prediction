# 🍽️ Restaurant Monthly Revenue Prediction

A machine learning project that analyzes restaurant business data and predicts **monthly revenue** using operational and business-related features.

## 📌 Project Overview

Understanding and predicting restaurant revenue can help businesses make better decisions about customers, pricing, and marketing.

In this project, we explore a restaurant dataset, clean and analyze the data, identify the features most strongly related to monthly revenue, and build **Linear Regression models** to predict revenue.

The project follows a complete data science workflow:

**Data Understanding → Data Cleaning → Exploratory Data Analysis → Statistical Analysis → Feature Selection → Model Training → Model Evaluation → Business Insights**

---

## 🎯 Objectives

The main objectives of this project are to:

* Understand the factors that influence restaurant monthly revenue.
* Explore relationships between business features and revenue.
* Identify the most useful predictors.
* Clean and prepare the dataset for machine learning.
* Build and compare two Linear Regression models.
* Evaluate model performance using multiple metrics.
* Select the better model based on both performance and simplicity.

---

## 📊 Dataset

The dataset contains **1,000 restaurant records** and includes the following features:

| Feature                     | Description                                  |
| --------------------------- | -------------------------------------------- |
| `Number_of_Customers`       | Number of customers served                   |
| `Menu_Price`                | Restaurant menu price                        |
| `Marketing_Spend`           | Amount spent on marketing                    |
| `Cuisine_Type`              | Type of cuisine                              |
| `Average_Customer_Spending` | Average amount spent by each customer        |
| `Promotions`                | Whether promotions were used                 |
| `Reviews`                   | Number of customer reviews                   |
| `Monthly_Revenue`           | Monthly restaurant revenue — target variable |

### Data Cleaning

During data quality analysis:

* No missing values were found.
* No duplicate records were found.
* **5 observations contained negative monthly revenue**, which were treated as invalid and removed.
* `Cuisine_Type` was removed after statistical analysis showed no significant relationship with revenue.

After cleaning, the dataset contained **995 observations**.

---

## 🔎 Exploratory Data Analysis

The exploratory analysis showed that:

### Number of Customers

`Number_of_Customers` is the strongest predictor of revenue, with a correlation of approximately **0.75**.

This indicates a strong positive relationship: restaurants serving more customers generally generate higher monthly revenue.

### Menu Price

`Menu_Price` has a positive but weaker relationship with revenue, with a correlation of approximately **0.26**.

### Marketing Spend

`Marketing_Spend` also has a positive relationship with revenue, with a correlation of approximately **0.27**.

### Other Features

`Average_Customer_Spending` and `Reviews` showed very weak relationships with monthly revenue in this dataset.

Statistical tests also showed:

* `Cuisine_Type`: **ANOVA p ≈ 0.85** → no statistically significant difference in revenue between cuisine types.
* `Promotions`: **t-test p ≈ 0.64** → no statistically significant difference in revenue between promoted and non-promoted restaurants.

These findings were used to guide feature selection for the machine learning models.

---

## 🤖 Machine Learning Models

Two Linear Regression models were developed.

### Model A — All Features

Model A uses all available predictors after data cleaning:

* Number of Customers
* Menu Price
* Marketing Spend
* Average Customer Spending
* Reviews
* Promotions

### Model B — Selected Features

Model B uses only the three strongest predictors identified during the exploratory analysis:

* Number of Customers
* Menu Price
* Marketing Spend

The purpose of comparing these models is to determine whether removing weak predictors can create a simpler model without reducing performance.

---

## 📈 Model Evaluation

The models were evaluated using:

* **R²** — measures how much of the variation in revenue is explained by the model.
* **MAE (Mean Absolute Error)** — average absolute difference between actual and predicted revenue.
* **RMSE (Root Mean Squared Error)** — measures prediction error while giving more weight to larger errors.

### Results

| Metric   | Model A |    Model B |
| -------- | ------: | ---------: |
| **R²**   |  0.6504 | **0.6545** |
| **MAE**  |  $46.92 | **$46.53** |
| **RMSE** |  $59.76 | **$59.41** |

### Model Comparison

Model B performs slightly better across all three metrics.

Its:

* **R² is higher**
* **MAE is lower**
* **RMSE is lower**

More importantly, Model B achieves this performance using only **3 features instead of 6**.

Therefore, **Model B is the preferred model** because it is simpler, easier to interpret, and provides slightly better predictive performance on the test data.

---

## 📉 Actual vs Predicted Revenue

The project also includes an **Actual vs Predicted Revenue** visualization for both models.

The dashed diagonal line represents perfect predictions, where:

**Actual Revenue = Predicted Revenue**

The closer the points are to this line, the better the model's predictions.

---

## 💡 Key Business Insights

The analysis suggests that **customer volume is the most important factor associated with restaurant revenue** in this dataset.

The results also indicate that:

1. Increasing customer traffic is strongly associated with higher revenue.
2. Menu pricing has a positive but weaker relationship with revenue.
3. Marketing spending has a positive relationship with revenue.
4. Cuisine type does not appear to significantly affect revenue in this dataset.
5. Promotions did not show a statistically significant revenue difference.
6. A smaller set of carefully selected features can perform as well as, or slightly better than, using all available predictors.

---

## 🏁 Final Conclusion

This project demonstrates a complete machine learning workflow for restaurant revenue prediction.

The analysis identified **Number of Customers, Menu Price, and Marketing Spend** as the most useful predictors among the available features. After comparing two Linear Regression models, **Model B was selected as the final model** because it achieved slightly better performance while using fewer features.

The final model achieved an **R² of approximately 0.65**, meaning it explains around 65% of the variation in monthly revenue in the test data.

The model provides a useful baseline for revenue prediction, but additional variables could improve its performance. Future versions could include factors such as **restaurant location, seasonality, holidays, competition, operating costs, and detailed customer behavior**.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas** — data manipulation
* **NumPy** — numerical operations
* **Matplotlib** — data visualization
* **Seaborn** — exploratory visualization
* **SciPy** — statistical testing
* **Scikit-learn** — machine learning and model evaluation
* **Jupyter Notebook** — development environment

---

## 📁 Project Structure

```text
Restaurant-Monthly-Revenue-Prediction/
│
├── Restaurant_Monthly_Revenue_Prediction.ipynb
├── Restaurant_revenue.csv
└── README.md
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Restaurant-Monthly-Revenue-Prediction
```

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open

```text
Restaurant_Monthly_Revenue_Prediction.ipynb
```

Run the notebook cells from top to bottom.

---

## 👤 Author

**NourEldin Islam**

Machine Learning & Data Science Project

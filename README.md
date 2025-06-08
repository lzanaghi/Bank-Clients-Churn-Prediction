# Customer Churn Prediction with kNN, Naive Bayes and Decision Tree

This project analyzes and builds predictive models to identify bank customers likely to churn (cancel services) based on various personal and account-related features.

## 🔗 Open in Google Colab

Click below to run this project directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

---

## 📊 Dataset Description

The dataset used is `Churn_Modelling.csv`, containing information about 10,000 customers of a bank. Key features include:

| Feature | Description |
|--------|-------------|
| `RowNumber` | Row index |
| `CustomerId` | Unique customer ID |
| `Surname` | Last name |
| `CreditScore` | Customer’s credit score |
| `Geography` | Country of residence |
| `Gender` | Gender |
| `Age` | Age |
| `Tenure` | Time as a customer |
| `Balance` | Bank account balance |
| `NumOfProducts` | Number of products held |
| `HasCrCard` | Has a credit card |
| `IsActiveMember` | Whether the customer is active |
| `EstimatedSalary` | Estimated salary |
| `Exited` | Whether the customer left (1) or stayed (0) |

---

## 🔎 Exploratory Data Analysis (EDA)

- ✅ No missing or duplicate values were found.
- 📈 KDE and count plots were used to analyze relationships between features and churn.
- Key findings:
  - Customers aged 40–70 are more likely to churn.
  - Having more products (especially 3 or more) increases the churn probability.
  - Non-active members are significantly more likely to leave.
  - German customers have a higher churn rate; French customers are less likely to churn.
  - Female customers have a higher churn rate compared to males.
  - Account balance has some correlation with churn.
  - Estimated salary and the remaining columns does not show meaningful correlation with churn.

---

## ⚙️ Data Preprocessing

- **Class Balancing**: The dataset was balanced using undersampling of the majority class.
- **Column Removal**: Dropped non-informative columns like `CustomerId`, `RowNumber`, and `Surname`.
- **Categorical Encoding**:
  - `Geography`: France → 0, Spain → 1, Germany → 2
  - `Gender`: Male → 0, Female → 1
- **Feature Selection**: Removed `CreditScore`, `Tenure`, and `HasCrCard` for Naive Bayes model.
- **Normalization**: Applied `StandardScaler` to scale features before training.

---

## 🤖 Model Training 

- The three classifiers were trained using:
  - 85% training data
  - 15% testing data
  - Scaled numerical features

### Evaluation Metrics:
- **Accuracy**
- **Classification Report (Precision, Recall, F1-score)**
- **Confusion Matrix**

---

📈 Results Summary
The model successfully learned to distinguish between customers who stayed and those who left, even in the presence of class imbalance. Feature analysis helped inform important predictors such as activity status, number of products, and geography.

---

✍️ Author
Developed by Ronaldo S. Antonio; Vitor A. P. Vieira; Jhonatan F. Novais.
For academic and research purposes.

📁 License
This project is licensed under the MIT License.

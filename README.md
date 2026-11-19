from pathlib import Path
import pypandoc

readme = r'''<div align="center">

# 🛡️ Fraud Detection in Financial Transactions
### Data Analysis & Machine Learning Insights

**Identifying suspicious financial transactions using exploratory data analysis and machine learning.**

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)

</div>

---

## 📌 1. Components

This project follows a practical data science workflow, from understanding transaction data to evaluating machine learning classification models.

| Component | Description |
|---|---|
| 📥 Data Loading | Import the financial transaction dataset and inspect its structure. |
| 🔎 Exploratory Data Analysis (EDA) | Examine transaction patterns, distributions, class balance, and potential fraud indicators. |
| 🧹 Data Preprocessing | Prepare the data for analysis and machine learning. |
| ⚖️ Imbalanced Data Handling | Apply **SMOTE** to address the imbalance between fraudulent and legitimate transactions. |
| 🤖 Model Building | Train and compare Logistic Regression, Decision Tree, Support Vector Machine (SVM), and Random Forest models. |
| 📊 Model Evaluation | Compare model performance using classification metrics and visual analysis. |

### 🧰 Technology Stack

- **Programming:** Python
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn
- **Imbalanced Data:** imbalanced-learn (SMOTE)
- **Environment:** Jupyter Notebook

---

## 🎯 2. Problem Statements

Financial fraud can cause monetary losses, reduce customer trust, and create operational challenges for financial institutions.

The key problem statements addressed in this project are:

1. **Fraud identification:** How can fraudulent transactions be distinguished from legitimate transactions using historical transaction data?
2. **Transaction pattern analysis:** Which transaction characteristics and patterns may help identify suspicious activity?
3. **Class imbalance:** How can a machine learning model learn effectively when fraudulent transactions are much less frequent than legitimate transactions?
4. **Model selection:** Which classification algorithm provides the strongest performance for this fraud detection task?
5. **Reliable evaluation:** How can model performance be assessed beyond accuracy, especially when missing a fraudulent transaction can be costly?

---

## 💡 3. Solution

The project implements a machine learning workflow to analyze financial transactions and classify them as potentially fraudulent or legitimate.

### 🔄 Project Workflow

```text
Financial Transaction Dataset
            │
            ▼
       Data Loading
            │
            ▼
 Exploratory Data Analysis
            │
            ▼
    Data Preprocessing
            │
            ▼
      Train-Test Split
            │
            ▼
       SMOTE Handling
            │
            ▼
     Model Training
            │
            ▼
   Model Evaluation
            │
            ▼
    Model Comparison
```

### 🤖 Machine Learning Algorithms

The following classification algorithms are implemented and compared:

- **Logistic Regression:** A baseline classification algorithm for predicting fraud and non-fraud transactions.
- **Decision Tree:** Learns decision rules from transaction attributes to classify suspicious activity.
- **Support Vector Machine (SVM):** Identifies a decision boundary between fraudulent and legitimate transactions.
- **Random Forest:** Combines multiple decision trees to improve classification performance and robustness.

### ⚖️ Handling Class Imbalance with SMOTE

Fraud datasets commonly contain significantly fewer fraudulent transactions than legitimate ones. This imbalance can cause a model to favor the majority class.

**Synthetic Minority Over-sampling Technique (SMOTE)** is used to generate synthetic examples of the minority class during model training.

> **Important:** SMOTE should be applied only to the training data after the train-test split. The test data should retain its original class distribution to provide a realistic evaluation.

---

## 📁 4. Folder Structure

The current GitHub repository is organized as follows:

```text
Fraud-Detection-in-Financial-Transactions/
│
├── 📓 Fraud Detection in Financial Transactions -
│   └── Data Analysis & Machine Learning Insights.ipynb
│       # EDA, preprocessing, SMOTE, model training,
│       # evaluation, and analysis
│
├── 📄 financial_fraud_dataset.csv
│   # Financial transaction dataset used in the project
│
└── 📘 README.md
    # Project documentation
```

### 📂 File Description

| File | Purpose |
|---|---|
| `Fraud Detection in Financial Transactions - Data Analysis & Machine Learning Insights.ipynb` | Main notebook containing the complete analysis and machine learning workflow. |
| `financial_fraud_dataset.csv` | Dataset used for transaction analysis and model development. |
| `README.md` | Documentation describing the project, methodology, and results. |

### ▶️ How to Run the Project

1. Clone the repository:

   ```bash
   git clone https://github.com/SurajSitoula2000/Fraud-Detection-in-Financial-Transactions---Data-Analysis-Machine-Learning-Insights.git
   ```

2. Navigate to the project directory:

   ```bash
   cd Fraud-Detection-in-Financial-Transactions---Data-Analysis-Machine-Learning-Insights
   ```

3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
   ```

4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open the project notebook and run the cells sequentially.

---

## 📈 5. Outcomes

The project compares four machine learning algorithms to identify the model that performs best on the financial fraud classification task.

### 🏆 Model Performance Comparison

| Machine Learning Model | Accuracy |
|---|---:|
| Logistic Regression | 91.2% |
| Decision Tree | 93.5% |
| Support Vector Machine (SVM) | 92.1% |
| **Random Forest** | **95.4%** |

<details>
<summary>📊 View key findings</summary>

- Random Forest achieved the highest reported accuracy among the four evaluated models.
- Decision Tree also performed competitively.
- SMOTE was used to address the class imbalance during model development.
- The comparison demonstrates how different classification algorithms perform on the same fraud detection task.

</details>

### ✅ Key Learnings

- Performed exploratory data analysis on financial transaction data.
- Identified the importance of class distribution and data quality in fraud detection.
- Applied SMOTE to address imbalanced classification data.
- Built and compared multiple supervised machine learning classification models.
- Evaluated model performance and identified Random Forest as the best-performing model by reported accuracy.

> **Note:** Accuracy alone is not sufficient to judge a fraud detection model. Precision, recall, F1-score, and the confusion matrix should also be reviewed. In particular, recall for the fraud class is important because it indicates how many actual fraudulent transactions are detected.

---

<div align="center">

### ⭐ If you find this project useful, consider giving the repository a star!

**Built with Python, Data Analysis & Machine Learning.**

</div>
'''
out = Path("/mnt/data/README.md")
pypandoc.convert_text(readme, "md", format="md", outputfile=str(out), extra_args=["--standalone"])
print(f"Created: {out} ({out.stat().st_size:,} bytes)")

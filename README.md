# Diabetes Prediction Project

This project details a complete machine learning workflow to predict the onset of diabetes based on a set of demographic and health indicators. The entire process, from data exploration to model training and interactive deployment, is contained within the `Diabetes_prediction.ipynb` notebook.

## Table of Contents

- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Models & Results](#models--results)
- [Deployment](#deployment)
- [Dependencies](#dependencies)
- [How to Run](#how-to-run)

-----

## Dataset

The model is trained on the `diabetes_prediction_dataset.csv` file, which includes the following features:

- `gender`: Sex of the individual (Female, Male, Other)
- `age`: Age of the individual
- `hypertension`: Whether the individual has hypertension (0: No, 1: Yes)
- `heart_disease`: Whether the individual has heart disease (0: No, 1: Yes)
- `smoking_history`: The individual's smoking status
- `bmi`: Body Mass Index
- `HbA1c_level`: Hemoglobin A1c level (average blood sugar)
- `blood_glucose_level`: Current blood glucose level

**Target Variable:**
- `diabetes`: (0: Non-diabetic, 1: Diabetic)

-----

## Project Workflow

1. **Import Libraries:** All necessary libraries such as `pandas`, `numpy`, `matplotlib`, `seaborn`, `sklearn`, `category_encoders`, and `gradio` are imported.
2. **Load Data:** The `diabetes_prediction_dataset.csv` is loaded into a pandas DataFrame.
3. **Exploratory Data Analysis (EDA):**
   - The notebook performs an initial analysis using `.info()`, `.describe()`, and `.isnull().sum()` (confirming no missing values).
   - Visualizations like histograms, count plots, and a heatmap are generated to understand feature distributions and relationships.
4. **Data Preprocessing:**
   - Categorical features (`gender`, `smoking_history`) are converted into numerical format using `OneHotEncoder`.
   - Original categorical columns are dropped.
5. **Train-Test Split:** Dataset split: 80% training, 20% testing.
6. **Feature Scaling:** Standardization using `StandardScaler`, especially for models like KNN and SVC.

-----

## Models & Results

Five different classification models were trained and evaluated using accuracy on the test set.  
The **Random Forest Classifier** achieved the highest accuracy.

### **Accuracy Scores (from the notebook):**

| Model | Accuracy Score |
|-------|----------------|
| **Random Forest Classifier** | **96.71%** |
| K-Nearest Neighbors (KNN) | 93.99% |
| Logistic Regression | 93.32% |
| Support Vector Classifier (SVC) | 93.14% |
| Gaussian Naive Bayes | 68.78% |

**Final Model Selected:**  
a) Random Forest Classifier (highest accuracy)  
b) Saved as `model.pkl`  

-----

## Deployment

- **Model Saving:** The top-performing model (`RandomForestClassifier`) is saved as `model.pkl` using Python’s `pickle`.
- **Web Interface:**  
  A clean, interactive UI is built using **Gradio**, allowing the user to input health parameters and get instant diabetes predictions.

-----

## Dependencies

Required Python packages:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `category_encoders`
- `gradio`
- `jupyter`

Install them using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn category_encoders gradio jupyter

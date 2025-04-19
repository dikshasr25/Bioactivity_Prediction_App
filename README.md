# iQSAR Model for IDO1 Inhibitors

This project involves the development of a machine learning-based **iQSAR model** to predict the biological activity (pIC50) of IDO1 (Indoleamine 2,3-dioxygenase 1) inhibitors using **Random Forest Regression** and **PubChem fingerprints**.

---

## 📁 Files in this Project

- `bioactivity_data_3class_pIC50_pubchem_fp.csv`: Dataset containing molecular fingerprints and pIC50 values.
- `descriptor_list.csv`: Filtered descriptor list after removing low-variance features.
- `IDO1_model.pkl`: Trained Random Forest model saved as a pickle file.
- `README.md`: Documentation for understanding and reproducing the workflow.

---

## 📊 Model Workflow

### 1. Data Loading
Load a CSV dataset containing molecular fingerprints and corresponding pIC50 values.

This is the starting point for model building.

### 2. Feature and Target Separation
Split the dataset into:

X: Descriptor (fingerprint) variables.

Y: Target variable (pIC50 values).

### 3. Feature Selection
Remove low-variance features that are unlikely to be informative.

Improves model performance and reduces overfitting.

Save the list of selected descriptors for future use.

### 4. Model Building
Train a Random Forest Regressor using the selected descriptors.

Use 500 trees (n_estimators=500) and a fixed random seed for reproducibility.

### 5. Model Evaluation
Calculate the coefficient of determination (R²) and Mean Squared Error (MSE) on the training set.

These metrics help assess model accuracy.

### 6. Model Prediction
Predict pIC50 values using the trained model on the training data.

Generate an array of predicted values.

### 7. Model Performance Visualization
Create a scatter plot of experimental vs. predicted pIC50 values.

Add a trendline to visualize how well the predictions align with actual values.

### 8. Model Saving
Serialize the trained model using Python's pickle module.

Save it as a .pkl file (IDO1_model.pkl) for later use in prediction or deployment.

## Output Files
descriptor_list.csv: CSV containing selected descriptors (features) after low-variance filtering.

IDO1_model.pkl: Trained Random Forest model stored as a pickle object.
---

## ✅ Results Summary

- **Model**: Random Forest Regressor
- **R² Score**: 0.83
- **Mean Squared Error**: 0.37
- **Features Used**: 218 descriptors (from initial 881)

---

## 💡 Future Improvements

- Perform cross-validation for better generalization.
- Apply hyperparameter tuning (e.g., GridSearchCV).
- Add external validation dataset.
- Explore other machine learning algorithms (e.g., SVR, XGBoost).

---

## 📌 Requirements

- Python 3.x
- pandas
- scikit-learn
- matplotlib
- numpy
- pickle

Install dependencies using:
```bash
pip install pandas scikit-learn matplotlib numpy
```

---

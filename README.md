# Human Activity Recognition Using Smartphone Data
This project classifies human activities (such as Walking, Standing, etc.) based on smartphone sensor data using machine learning models. It includes data preprocessing, feature selection, model training, and a simple GUI for predictions on new datasets.

## 📂 Dataset
- Source: UCI Human Activity Recognition Dataset
- Files Used:
  - train.csv – Used for training and evaluation.
  - test.csv – Used for final predictions.

## ✅ Features
- 542 sensor signal features from smartphone accelerometers and gyroscopes.
- Labels: 6 human activities (e.g., Standing, Sitting, Walking, etc.)

## 🛠️ Steps Implemented
1. Data Loading & Cleaning
- Loaded train and test datasets.
- Removed 21 duplicate columns.
- Confirmed no missing values.

2. Exploratory Data Analysis
- Visualized activity distribution using seaborn countplot.

3. Preprocessing
- Dropped label column (Activity) for test data.
- Encoded activity labels with LabelEncoder.

4. Train-Test Split
- Split data into 80% training and 20% testing.

5. Modeling
- Trained models:
- Logistic Regression – Accuracy: 98.02%
- Random Forest – Accuracy: 98.16%

6. Feature Selection
- Filter Method: Selected top 200 features using ANOVA F-score (SelectKBest).
- Wrapper Method: Applied RFE on filtered features to select best 100.

7. Final Model
- Trained a Random Forest classifier on the selected 100 features.
- Final test accuracy: 97.69%

8. Model Saving
- Saved models and selectors using joblib:
  - model_rfe
  - k_best_selector
  - rfe_selector

🖥️ GUI Interface
Built with Tkinter:
- Allows users to load a .csv file for prediction.
- Automatically preprocesses input, applies feature selection, and predicts activity labels.
- Saves the output as a new .csv file with predictions.

🎯 Predicted Classes
```bash
0 → Standing  
1 → Sitting  
2 → Laying  
3 → Walking_downstairs  
4 → Walking_upstairs  
5 → Walking
```
## ▶️ How to Run
1. Ensure required libraries are installed:
```bash
pip install pandas scikit-learn matplotlib seaborn joblib
```
2. Run the main script
```bash
python your_script_name.py
```
3. Use the GUI
- Click "Open CSV File" to select a new dataset.
- Processed predictions will be saved to a user-specified CSV file.

## 📁 Output
A .csv file with an additional column Predicted_target that shows the predicted activity for each row.

📌 Notes
- Your input .csv file must match the test dataset structure with the same feature names.
- The activity column is optional and will be dropped during processing if present.



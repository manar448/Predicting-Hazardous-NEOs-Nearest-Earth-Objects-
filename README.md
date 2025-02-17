# 🌌 Predicting Hazardous NEOs (Near-Earth Objects)

## 📊 Project Overview
This project focuses on predicting whether a Near-Earth Object (NEO) is hazardous to Earth. The dataset, sourced from NASA and available on [Kaggle](https://www.kaggle.com/datasets/ivansher/nasa-nearest-earth-objects-1910-2024/data)., spans from 1910 to 2024, tracking 338,199 objects. The main goal is to develop a machine-learning model that accurately classifies these NEOs into hazardous and non-hazardous categories, crucial for planetary defense.

## 📋 Dataset Information
The dataset consists of 338,199 records of NEOs tracked by NASA, including information such as the NEO’s size, velocity, distance from Earth, and whether NASA classified the object as hazardous.

### 🔑 Key Features:
- **neo_id**: Unique identifier for each NEO.
- **name**: Name of the NEO.
- **absolute_magnitude**: Brightness of the NEO.
- **estimated_diameter_min**: Minimum estimated diameter of the NEO (km).
- **estimated_diameter_max**: Maximum estimated diameter of the NEO (km).
- **orbiting_body**: The celestial body the NEO is orbiting.
- **relative_velocity**: Velocity of the NEO relative to Earth (km/h).
- **miss_distance**: Distance between Earth and the NEO at its closest point (km).
- **is_hazardous**: Boolean value indicating if the NEO is classified as hazardous (True/False).

## 🛠️ Project Structure
The project consists of the following steps:

### 1. 🧹 Data Importing and Cleaning:
- Handled missing values by filling numeric columns with the median and categorical columns with the mode.

### 2. 📈 Exploratory Data Analysis (EDA):
- Created visualizations such as bar plots, histograms, and pie charts using libraries like Seaborn and Plotly to understand data distribution and relationships.
- Plotted a correlation matrix to identify relationships between numerical features.

### 3. ⚖️ Handling Class Imbalance:
- The dataset is highly imbalanced, with far fewer hazardous objects compared to non-hazardous ones.
- Applied SMOTE (Synthetic Minority Over-sampling Technique) to balance the classes for improved model performance.

### 4. 🔍 Feature Selection:
- Selected features such as absolute_magnitude, estimated_diameter_min, estimated_diameter_max, relative_velocity, and miss_distance for model training.
- Dropped columns like neo_id, name, and orbiting_body as they do not provide predictive value.

### 5. 🏗️ Model Training:
- Built two machine learning models:
  - **Logistic Regression**
  - **DecisionTreeClassifier**
  - **KNeighborsClassifier**
  
models are trained and evaluated on a balanced dataset.

### 6. 📊 Evaluation:
- Evaluation is performed using metrics such as:
  - Accuracy
  - Precision
  - Recall
  - F1 Score
- Visualized the learning curves of the models to understand their performance on training and test sets.

## 🚀 Code Execution
1. **Install Necessary Packages**:
   ```bash
   pip install -r requirements.txt
   ```
2. **Run the Script**:
   Execute the Jupyter Notebook included in the repository. Ensure the dataset is downloaded.
   ```python
   # Load Data
   file_name = "nearest-earth-objects(1910-2024).csv"
   file_path = os.path.join(os.path.dirname(os.path.abspath(file_name)), file_name)
   ```
3. **Model Building**:
   Split the dataset into 80% training and 20% testing, then train both models:
   ```python
   from sklearn.linear_model import LogisticRegression, LinearRegression
   from sklearn.tree import DecisionTreeClassifier
   from sklearn.neighbors import KNeighborsClassifier

   # Model Building and Evaluation The Best Model Is The DecisionTree
   DTModel = DecisionTreeClassifier()
   ```

4. **Evaluation**:
   Evaluate both models using classification reports and confusion matrices:
   ```python
   from sklearn.metrics import classification_report, confusion_matrix, accuracy_score

   # Decision Tree Evaluation
   print(classification_report(y_test, y_pred))
   cm = confusion_matrix(y_test, y_pred)
   ```

## 🏆 Results and Evaluation
| Model                   | Accuracy | Precision | Recall | F1 Score |
|-------------------------|----------|-----------|--------|----------|
| Decision Tree           | 94.00%   | 0.94      | 0.94   | 0.94     |


## 📉 Confusion Matrix Visualization:
I plotted the confusion matrix to visually assess model performance.

## 📝 Conclusion
The dataset shows a significant imbalance between hazardous and non-hazardous NEOs, which was effectively managed using SMOTE. The RandomForestClassifier achieved an F1 Score of 96%, making it the best-performing model in this project. This project demonstrates a full pipeline from data cleaning and exploratory analysis to model building and evaluation, ready for real-world applications in planetary defense.

--- 

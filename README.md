# weather-data-analysis
Weather data analysis using Python and Linear Regression




1. Introduction

Weather data analysis plays a crucial role in understanding atmospheric conditions and predicting future weather patterns. This project focuses on analyzing a weather dataset using Python to extract meaningful insights and to build a basic machine learning model for rainfall prediction.

The analysis includes data loading, preprocessing, exploratory data analysis (EDA), visualization, handling missing values, and applying a Linear Regression model.



2. Objectives

The main objectives of this project are:

* To explore and understand the structure of the weather dataset
* To perform statistical and visual analysis of weather parameters
* To identify relationships between different weather variables
* To preprocess data for machine learning
* To build and evaluate a rainfall prediction model
* To document limitations of the dataset



 3. Software and Hardware Requirements

### 3.1 Software Requirements

* **Operating System**: Windows / Linux / macOS
* **Python Version**: Python 3.x
* **Anaconda Distribution**
* **Jupyter Notebook**

### 3.2 Python Libraries Used

* `pandas` – data manipulation
* `numpy` – numerical computation
* `matplotlib` – data visualization
* `seaborn` – advanced plotting
* `scikit-learn` – machine learning algorithms

---

4. Dataset Description

The dataset used is **weather.csv**, containing daily weather observations.

### Dataset Characteristics:

* **Number of rows**: 366
* **Number of columns**: 22
* **Data types**:

  * Numerical (temperature, rainfall, humidity, pressure, wind speed)
  * Categorical (wind direction, RainToday, RainTomorrow)

### Important Columns:

* `MinTemp`, `MaxTemp`
* `Rainfall`
* `Humidity9am`, `Humidity3pm`
* `WindSpeed9am`, `WindSpeed3pm`
* `RainToday`, `RainTomorrow`

⚠️ The dataset **does not contain date or month information**, which limits time-based analysis.



5. Workflow / Methodology

### Step 1: Importing Required Libraries

The required Python libraries were imported to handle data processing, visualization, and modeling.

### Step 2: Loading the Dataset

The CSV file was loaded into a Pandas DataFrame to allow structured data analysis.

**Outcome**: Dataset successfully loaded into the variable `df`.



### Step 3: Initial Data Exploration

* First few rows were displayed to understand data layout.
* Dataset structure and data types were examined.
* Missing values were identified.

**Key Observation**:

* Several columns contain missing (NaN) values.
* Categorical and numerical columns coexist.



### Step 4: Statistical Summary

Descriptive statistics were generated for numerical columns to understand:

* Mean
* Minimum and maximum values
* Standard deviation

This helped in identifying data spread and anomalies.



### Step 5: Exploratory Data Analysis (EDA)

#### Correlation Analysis

A correlation heatmap was created using numerical columns only to identify relationships between weather parameters.

**Result**:

* Strong correlations were observed between humidity, rainfall, and cloud cover.
* Temperature showed inverse relationship with rainfall.

---

### Step 6: Limitation in Monthly Analysis

The dataset does **not contain a Date or Month column**.

**Conclusion**:

> Monthly average maximum temperature cannot be calculated due to absence of temporal attributes in the dataset.

This limitation was clearly documented in the analysis.



### Step 7: Alternative Analysis

Instead of monthly analysis, average maximum temperature was analyzed based on rainfall occurrence (`RainToday`).

**Insight**:

* Non-rainy days generally show higher maximum temperatures compared to rainy days.



6. Data Preprocessing

### 6.1 Encoding Categorical Variables

Categorical variables such as wind direction and rainfall labels were converted into numerical format using **one-hot encoding**.

This step is necessary because machine learning models cannot process string values.


### 6.2 Feature and Target Selection

* **Target Variable**: `Rainfall`
* **Input Features**: All remaining numerical and encoded variables



### 6.3 Train–Test Split

The dataset was divided into:

* **Training set**: 80%
* **Testing set**: 20%

This allows evaluation of model performance on unseen data.



### 6.4 Handling Missing Values

During model training, an error occurred because Linear Regression does not support missing values.

**Solution**:

* Mean imputation was applied using `SimpleImputer` to replace missing values.

This step ensured the dataset was suitable for model training.



7. Model Building

### Model Used:

* **Linear Regression**

The model was trained using the processed training dataset to predict rainfall values.



 8. Model Evaluation

The trained model was evaluated using:

* **R² Score**
* **Root Mean Square Error (RMSE)**

### Results:

* **R² Score** ≈ 0.19
* **RMSE** ≈ 34.22

**Interpretation**:

* The low R² score indicates that rainfall prediction is complex and not well explained by a simple linear model.
* Rainfall depends on non-linear and dynamic weather factors.



9. Results and Discussion

* Successful data exploration and visualization were performed.
* Dataset limitations were correctly identified and documented.
* Proper preprocessing was required to handle missing and categorical data.
* Linear Regression provided limited accuracy, indicating the need for advanced models.



10. Conclusion

This project demonstrated the complete workflow of weather data analysis using Python. The absence of temporal data restricted monthly analysis, but meaningful insights were still obtained through alternative methods. Data preprocessing played a crucial role in successful model training. Although Linear Regression showed limited predictive power, the project effectively highlights the importance of data quality, preprocessing, and model selection in data science.



 11. Future Scope

* Use datasets with date and time information
* Apply advanced models such as Random Forest or Gradient Boosting
* Perform seasonal and trend analysis
* Improve accuracy using feature selection and scaling

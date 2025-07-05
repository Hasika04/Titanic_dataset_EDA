# Titanic_dataset_EDA
# Titanic Survival Prediction - Exploratory Data Analysis (EDA)

This project explores the **Titanic dataset** from Kaggle using **Python, Pandas, and Seaborn/Matplotlib** to uncover patterns in passenger survival. The goal is to perform **data cleaning**, **feature engineering**, and **visual analysis** to derive meaningful insights that could be useful in predictive modeling.

---

## Files in the Repository

- `titanic_eda.ipynb` – Jupyter Notebook with full EDA, data cleaning, feature engineering, and visualizations.
- `README.md` – This documentation file describing the steps and findings.

##  Tools and Libraries Used

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- 
## Project Workflow (A to Z)

### 1️) Load and Understand the Data
- Loaded the dataset into a Pandas DataFrame.
- Checked the structure, data types, null values, and basic stats.

### 2) Data Cleaning
- Handled missing values:
  - **Age** filled with median.
  - **Embarked** filled with mode.
  - **Cabin** column dropped.
- Changed datatype of Age to integer

### 3️) Feature Engineering
Created new informative features to enhance analysis:
- **FamilySize** = `SibSp + Parch + 1`
- **IsAlone** = 1 if `FamilySize == 1`, else 0
- **AgeBand** = Binned age into `Child`, `Teen`, `YoungAdult`, `Adult`, `Senior`
- **FareBand** = Fare quartiles (`Low`, `Mid`, `High`, `VeryHigh`)
- 
### 4️) Data Encoding
- Used `pd.get_dummies()` to one-hot encode `Sex`, `Embarked`, etc.
- Ensured all boolean columns were converted to integers.
- 
### 5) Univariate Analysis
- Plotted distributions of individual features: `Sex`, `Age`, `Pclass`, `Embarked`, `Fare`, `Survived`

### 6) Bivariate and Multivariate Analysis
- Analyzed how features affected survival:
  - `Sex` vs `Survived`
  - `Pclass` vs `Survived`
  - `AgeBand`, `FareBand` vs `Survived`
  - Heatmap of correlation matrix

### 7) Insights / Patterns

#### Highest Survival Rates:
- **Females** had much higher survival rates than males.
- **1st Class passengers** had higher survival rates than 2nd and 3rd.
- **Passengers with family** (not alone) were more likely to survive.

#### Other Findings:
- `Title` gave insight into age/gender and affected survival.
- Passengers from **Cherbourg (`Embarked = C`)** had slightly higher survival rates.
- Fare and age bands showed clear survival trends.

### 8) Conclusion
EDA revealed that:
- **Sex**, **Pclass**, and **FamilySize** are strong indicators of survival.
- Engineered features like **Ageband**, **IsAlone**, and **FareBand** improved understanding of patterns.
- These insights are highly valuable for building accurate predictive models in the future.

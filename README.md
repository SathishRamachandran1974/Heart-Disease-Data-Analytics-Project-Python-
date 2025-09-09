## ❤️Heart Disease Data Analytics Project (Python)  
   - This project applies Python-based data analytics to a clinical dataset of 918 patients to uncover key health risk factors and patterns associated with heart disease.
     Using Pandas, Matplotlib, and Seaborn, the project cleans, processes, and visualizes patient health metrics to derive actionable medical insights.

## Objective
   - The goal of this project is to analyze patient data across demographics, clinical features, and test results to identify factors correlated with heart disease.
     By combining statistical summaries with visualizations, the project highlights which patient attributes (age, cholesterol, blood pressure, etc.) have the
     strongest association with cardiac risk.
   - Key KPIs such as prevalence rates, cholesterol distribution, and risk ratios provide a quick overview, while categorical and numerical analyses allow deeper
     exploration of patient subgroups.

## Key ProjectGoals 
   - Analyze patient demographics and identify high-risk groups by age and sex.
   - Evaluate the impact of cholesterol, blood pressure, and blood sugar on heart disease risk.
   - Compare heart disease prevalence across chest pain types, ECG results, and exercise-induced angina.
   - Provide summary tables and visualizations for quick interpretation of medical patterns.
   - Build reproducible analytics using Python for healthcare research and reporting.

## Analysis Features
   - Data Cleaning – Removed duplicates, handled missing values, and ensured data quality.
   - Key Metrics Overview – Heart disease prevalence, age distribution, cholesterol categories.
   - Age Distribution – Histogram of patients across age groups.
   - Gender vs Heart Disease – Stacked bar chart comparing prevalence by sex.
   - Chest Pain Analysis – Visualization of heart disease distribution across chest pain types.
   - Cholesterol Levels – Categorized into Low, Normal, High; ~58% of high-cholesterol patients had heart disease.
   - Blood Pressure Categories – Donut chart showing risk by Low, Normal, and High BP.
   - Fasting Blood Sugar – Normal vs High sugar level distributions.
   - Resting ECG & Max Heart Rate – Associations with disease risk.
   - Exercise-Induced Angina – Proportion of patients experiencing angina during exercise.
   - Chest Pain vs Disease Table – Summary of counts and prevalence by pain type.

## Key Findings (from the Analysis)
   - Age & Gender: Middle-aged males had higher prevalence compared to females. 
   - Cholesterol: 58% of patients with high cholesterol were diagnosed with heart disease.
   - Blood Pressure: Patients with high BP showed a 58.4% prevalence rate.
   - Chest Pain: Asymptomatic (ASY) patients had the highest number of heart disease cases.
   - ercise-Induced Angina: Patients with angina during exercise were significantly more likely to have heart disease.
   - Overall Prevalence: Around half of the dataset population showed indicators of heart disease.

## Visualizations
   - Age distribution histogram
   - Heart disease by gender (stacked bar chart)
   - Chest pain type vs heart disease (bar chart)
   - Cholesterol distribution (bar chart by category)
   - Blood pressure distribution (donut chart)
   - Fasting blood sugar distribution (bar chart)
   - Resting ECG by heart disease (stacked bar chart) 
   - Max heart rate distribution (donut chart)
   - Exercise-induced angina distribution (donut chart)
   - Chest pain summary table
     
## Sample DataSet
   - Sample Data Preview
   
| Patient ID | Age | Sex | ChestPainType | RestingBP | Cholesterol | FastingBS | RestingECG | MaxHR | ExerciseAngina | Oldpeak | ST_Slope | HeartDisease |
|------------|-----|-----|---------------|-----------|-------------|-----------|------------|-------|----------------|---------|----------|--------------|
| 1          | 40  | M   | ATA           | 140       | 289         | 0         | Normal     | 172   | N              | 0.0     | Up       | 0            |
| 2          | 49  | F   | NAP           | 160       | 180         | 0         | Normal     | 156   | N              | 1.0     | Flat     | 1            |
| 3          | 37  | M   | ATA           | 130       | 283         | 0         | ST         | 98    | N              | 0.0     | Up       | 0            |
| 4          | 48  | F   | ASY           | 138       | 214         | 0         | Normal     | 108   | Y              | 1.5     | Flat     | 1            |
| 5          | 54  | M   | NAP           | 150       | 195         | 0         | Normal     | 122   | N              | 0.0     | Up       | 0            |
| 6          | 39  | M   | NAP           | 120       | 339         | 0         | Normal     | 170   | N              | 0.0     | Up       | 0            |
| 7          | 45  | F   | ATA           | 130       | 237         | 0         | Normal     | 170   | N              | 0.0     | Up       | 0            |
| 8          | 54  | M   | ATA           | 110       | 208         | 0         | Normal     | 142   | N              | 0.0     | Up       | 0            |
| 9          | 37  | M   | ASY           | 140       | 207         | 0         | Normal     | 130   | Y              | 1.5     | Flat     | 1            |
| 10         | 48  | F   | ATA           | 120       | 284         | 0         | Normal     | 120   | N              | 0.0     | Up       | 0            |

## Analysis-1
  - Imported libraries:
  - pandas → data manipulation
  - matplotlib & seaborn → visualization
  - Loaded dataset: Heart_Cleaned_Data.csv into a Pandas DataFrame.
  - Previewed the dataset using df.head() to display the first 5 rows.
  - Checked structure & metadata with df.info(), including:
  - Number of rows & columns (918 × 13)
  - Data types (int, float, object)
  - Non-null counts (verified no missing values)
  - Key observation : Dataset is clean, well-structured, and ready for further analysis (age, sex, cholesterol, blood pressure, chest pain type, etc.).
### 🐍 Python Code(Bedore Cleaning)
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# load dataset
df = pd.read_csv("Heart_Cleaned_Data.csv")

# preview first 5 rows
print(df.head())

# check structure and data types
print(df.info())
 ```
<img width="591" height="474" alt="Analysis 1" src="https://github.com/user-attachments/assets/84502e34-53fe-44cd-9974-f91f7f60d0da" />

## Analysis 2 – Data Cleaning    
   - This step focuses on **cleaning the heart disease dataset** to prepare it for accurate analysis and visualization.  
   - **Dataset Loaded**: `Heart_Cleaned_Data.csv` using **pandas**.  
   - **Removed blank cells** using `dropna()`.  
   - **Removed duplicate records** using `drop_duplicates()`.  
   - **Saved cleaned data** into a new file: `Heart_Cleaned-1.xlsx`.  
   - **Previewed cleaned dataset** using `to_string()` to verify changes.  
   - **Key Observation**: The dataset is now free from missing values and duplicates, ensuring reliability for further analysis.  
### 🐍 Python Code(After Cleaning)
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# load dataset
df = pd.read_csv("Heart_Cleaned.csv")

# removing the blankcell
df_cleaned = df.dropna()

# removing the duplicates
df_cleaned = df.drop_duplicates()

# Save to the same Excel file (overwrite)
df_cleaned.to_excel('Heart_Cleaned-1.xlsx', index=False)

# look into data
# print(df.to_string())
print(df_cleaned.to_string()) given this code in readme
```
<img width="873" height="539" alt="Analysis 2" src="https://github.com/user-attachments/assets/e85570de-828d-4b65-9417-bdf15c2ac5d0" />

## Analysis-3 (Age Distribution)
   - The histogram above visualizes the distribution of patients’ ages in the heart disease dataset. Key insights include:
      - Most patients fall within the 40–65 years age range, indicating that middle-aged and older adults are more represented in this dataset.
      - There are fewer patients in the younger (<30 years) and older (>70 years) age groups.
      - The distribution shows a slight right-skew, suggesting that extreme older ages are less common.
      - This analysis can help identify age-related patterns in heart disease prevalence and guide further statistical or predictive modeling.
### 🐍 Python Code
```python
plt.hist(df['Age'], bins=20, color="salmon", edgecolor="black")
plt.grid(True, linestyle="--", alpha=0.7)
plt.title("Age Distribution Of Patients")
plt.xlabel("Age")
plt.ylabel("Peoplecount")
plt.show()
```
<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/37da8286-bbf9-49fa-95d1-1c3ca20c9376" />

## Analysis-4(Gender Basis HeartDisease)
  - Visualizes heart disease cases grouped by gender.
  - Males have a higher number of heart disease cases compared to females.
  - Females show more patients without heart disease.
  - Highlights potential gender-based differences in heart disease prevalence.
  - Useful for demographic-based risk assessment and further analysis.
### 🐍 Python Code
```python
counts = pd.crosstab(df['Sex'], df['HeartDisease'])
counts.plot(kind='bar', stacked=True, color=['lightgreen', 'salmon'], edgecolor='black')
plt.grid(True, linestyle="--", alpha=0.7)
plt.title("Heart Disease Distribution by Sex")
plt.xlabel("Sex")
plt.ylabel("Peoplecount")
plt.show()
```
<img width="571" height="453" alt="image" src="https://github.com/user-attachments/assets/983bad32-5ebb-48ae-98c4-48cf52e08161" />

## Analysis-5(ChestPain Type Distribution)
 - Shows the distribution of heart disease cases across different chest pain types.
 - Certain chest pain types have a higher proportion of heart disease cases.
 - Patients with other chest pain types may have fewer cases, indicating lower risk.
 - Helps identify high-risk symptoms for heart disease.
 - Useful for symptom-based analysis and early detection insights.
### 🐍 Python Code
```python
counts = pd.crosstab(df['ChestPainType'], df['HeartDisease'])
counts.plot(kind='bar', stacked=True, color=['lightgreen','salmon'], edgecolor='black')
plt.grid(True, linestyle="--", alpha=0.7)
plt.title("ChestPain Type by HeartDisease")
plt.xlabel("Chestpain Type")
plt.ylabel("Peoplecount")
plt.show()
```
<img width="571" height="469" alt="image" src="https://github.com/user-attachments/assets/4d9ac363-013c-4f98-a090-5cd5bb19f648" />

## Analysis-6(Cholestral Level Distribution)
   - Categorizes cholesterol levels into Low (<200), Normal (200–239), and High (≥240).
   - Visualizes the number of patients in each cholesterol category.
   - Majority of patients may fall into the Normal or High cholesterol category.
   - High cholesterol is a major risk factor for heart disease.
   - This chart helps understand the distribution of cholesterol-related risk in the dataset.
### 🐍 Python Code
```python
def cholesterol_category(chol):
    if chol < 200:
        return 'Low'
    elif 200 <= chol < 240:
        return 'Normal'
    else:
        return 'High'

df['CholCategory'] = df['Cholesterol'].apply(cholesterol_category)
chol_counts = df['CholCategory'].value_counts().reindex(['Low','Normal','High'])
plt.bar(chol_counts.index, chol_counts.values, color=['lightblue','lightgreen','salmon'],edgecolor='black')
plt.title('Distribution of Cholesterol Levels')
plt.xlabel('Cholesterolcategory')
plt.ylabel('Peoplecount')
plt.show()
```
<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/185c1570-6934-42ec-8827-b5653c2937b9" />



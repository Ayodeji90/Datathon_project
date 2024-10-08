## PROBLEM STATEMENT
There is a significant gap in understanding the factors that impact students' academic performance, particularly in African secondary schools.
By analyzing key data points such as student demographics, attendance, and exam scores, we aim to identify patterns that contribute to poor performance and provide strategies for improvement.

## DATA COLLECTION AND STORAGE
Data Collection Methodology
We used a Questionnaire as the primary data collection method. The survey gathered data on various student factors including:

[Demographics (age, gender, background)](https://forms.gle/g4MAJrnQBRzuC4VC6)

[Attendance records](https://forms.gle/Ds8E7own3QyGCxRv9)

[Exam results and study patterns](https://forms.gle/Ly9MEAfZvVkm6Amc8)

[Socioeconomic status,Learning environment and resources](https://forms.gle/iQ3k18PgESB5zfMf8)

#### Tools Used for Data Collection
Google Forms: The questionnaire was distributed through Google Forms, which collected responses directly from students and educators.
Google Sheets API: Responses were automatically fetched from Google Sheets, connected to the form, using the Google Sheets API.

#### Data Storage
The collected data was stored in relational databases to allow for easy querying and analysis. We explored Google BigQuery for  storage solutions:

Google BigQuery: Used for handling large-scale data due to its scalability and support for complex SQL queries.


## DATA ANALYSIS
In this section, we delve into the comprehensive data analysis and visualization conducted using Microsoft Power BI. The primary objective was to extract meaningful insights from the collected data to identify factors influencing student performance and to visualize these insights for stakeholders in an accessible manner.

 Data Preparation for Power BI
              Data Importation
Data Sources: The cleaned and transformed data from the ETL process was exported into CSV files and directly imported into Power BI. The datasets included:
Student demographic data
Academic records (exam scores, attendance)
Socioeconomic status information
Study habits and resource availability

 ## [Observations on the PowerBI charts](https://github.com/Ayodeji90/Datathon_project/blob/main/Software_Engineering/Datathon/powerBI_visualization.pdf)
   1. Jamb scores by Attendance status
Observation: The average jamb score of students with very poor attendance status is higher than student with regular attendance

2. JAMB Score by Extracurricular Involvement and Disciplinary Issue
Observation: Students involved in extracurricular activities to a higher degree tend to have higher average JAMB scores. Having disciplinary issues generally correlates with lower scores.

3. JAMB Score by Exam Status and Study Habits
Observation: students with average study habits are associated with higher JAMB scores, and students who passed the exam had significantly higher average scores compared to those who failed.

4. Average of JAMB Score by Understanding of Material (1-3)
Observation: student with rare understanding of the material have slightly higher average jamb score

5. Exam Status by Class Participation
Observation: moderate and active participation in class correlates with higher exam pass rates compared to students who rarely participate.

6. JAMB Score by Academic Performance before JAMB/WAEC
Observation: Students with good and poor academic performance prior to JAMB have the highest JAMB scores compare to student with excellent and fair performance before jamb


The second page 
7. JAMB Score by Family Income Range and Exam Status
Observation: Higher family income is associated with better JAMB scores, with more students passing the exam in the higher income groups.

8. JAMB Score by Living Conditions and Exam Status
Observation: Students with moderate living conditions appear to correlate with higher JAMB scores and better exam outcomes.

9. JAMB Score by Age
Observation: JAMB scores vary slightly with age, with older students tending to perform slightly better.

10. Average of JAMB Score by Health Challenge
Observation: Students without health challenges have higher average JAMB scores.

11. Daily Self-Study Hours vs JAMB Score and Parent Education Level
Observation: There is a positive correlation between longer self-study hours and higher JAMB scores, with students whose parents had tertiary education performing the best.

12. Average of JAMB Score by Parent Engagement with School/Teachers.
Observation: Lower parental engagement with school/teachers is associated with slightly higher average JAMB scores.




# Predicting Student Exam Performance Using Machine Learning
 OVERVIEW
This aspect aims to predict students' exam status (pass/fail) based on various academic and personal factors using five different machine learning models. 
The prediction helps identify students at risk and provides personalized advice to improve their exam outcomes.

[Here is the python notebook]()

 [DATASET](https://github.com/Ayodeji90/Datathon_project/blob/main/Software_Engineering/Datathon/data.csv)
The dataset contains multiple features that impact student exam performance. Key features include:

Health Challenge
Class Participation
Academic Performance
Study Habits
Attendance Status
Family Income Range
Parent Education Level
Motivation for JAMB/WAEC
Living Conditions
Exam Status (Target Variable)

 DATA PROCESSING
Handling Missing Values: Missing values in categorical columns were filled appropriately (e.g., 'Moderate' for extracurricular involvement).
Label Encoding: Categorical variables were encoded into numerical format using LabelEncoder for model compatibility.
Train-Test Split: The data was split into 80% training and 20% testing using train_test_split.


 MODEL SELECTION
We utilized five machine learning models for this task:
Logistic Regression
Decision Tree Classifier
Random Forest Classifier
Support Vector Machine (SVM)
Gradient Boosting Classifier


 MODEL TRAINING
Each model was trained using the preprocessed training data and 100% accuracy was acheived

 Here’s a brief on model settings:
Logistic Regression: Used max_iter=1000 for convergence.
Random Forest: Trained with 100 estimators (n_estimators=100).

MODEL EVALUATION
Each model was evaluated on the test set using:
Confusion Matrix
Classification Report (Precision, Recall, F1-Score, Accuracy)
All models achieved 100% accuracy, which was consistent across the test set, indicating strong model performance.

The trained models were saved as .pkl files for integration into future applications using the joblib library.


### Students Performance |Trends and insight 
Python + Pandas + NumPy + Matplotlib + Seaborn + Jupyter Notebook

### Project Overview 
A student performance dataset containing variables such as study hours, attendance, previous scores, parental education, and access to resources, used to analyze patterns and identify key factors influencing academic outcomes.

### Tools & Technologies
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

### Dataset Overview

| student_id | gender | age | study_hours_per_week | attendance_rate | parent_education | internet_access | extracurricular | previous_score | final_score | passed |
| ---------- | ------ | --- | -------------------- | --------------- | ---------------- | --------------- | --------------- | -------------- | ----------- | ------ |
| STU0001    | Male   | 15  | 25                   | 63.8            | Bachelor         | Yes             | Yes             | 41             | 67          | Yes    |
| STU0002    | Female | 15  | 2                    | 54.7            | Bachelor         | Yes             | Yes             | 83             | 28          | No     |
| STU0003    | Female | 19  | 10                   | 90.5            | High School      | Yes             | No              | 73             | 49          | No     |
| STU0004    | Male   | 16  | 26                   | 66.8            | High School      | No              | Yes             | 75             | 70          | Yes    |
| STU0005    | Female | 15  | 25                   | 73.0            | High School      | No              | Yes             | 67             | 77          | Yes    |

### Python Exploratory Process 
This project followed a structured data science workflow, including data loading, cleaning, and exploratory analysis. The dataset was preprocessed by handling missing values, removing duplicates, and standardizing formats. Exploratory Data Analysis (EDA) was conducted using statistical summaries and visualizations to uncover patterns, relationships, and key factors influencing student performance.

### Exploratory Analysis (Python)
1. Load the dataset
```python
student_performance = pd.read_csv ('Desktop/student_performance.csv')
```
2. Preview your data
```python
student_performance.head()
student_performance.info()
student_performance.shape
```
<img width="1708" height="532" alt="Screenshot 2026-04-27 221425" src="https://github.com/user-attachments/assets/3ef8d40d-693a-4471-a3f8-9e9149115cbb" />
<img width="1798" height="146" alt="Screenshot 2026-04-27 221456" src="https://github.com/user-attachments/assets/824ac008-cf74-4b4e-baa0-c6cc752ad0d7" />
<img width="1776" height="662" alt="Screenshot 2026-04-27 221508" src="https://github.com/user-attachments/assets/547ad6d2-aa3d-499a-a0db-ed2b07e0dcf8" />
<img width="1775" height="443" alt="Screenshot 2026-04-27 221520" src="https://github.com/user-attachments/assets/bf7dd8ca-4bc0-429c-9836-f318baab7ac6" />
<img width="1774" height="414" alt="Screenshot 2026-04-27 221530" src="https://github.com/user-attachments/assets/68e513c3-d0d4-480f-9719-ac9af1515177" />

3. Check missing values
```python
student_performance.isnull().sum()
```
<img width="1801" height="543" alt="Screenshot 2026-04-27 221819" src="https://github.com/user-attachments/assets/8be287b9-5291-4499-bbac-00a5915c0c92" />

4. Remove duplicates
```python
student_performance.drop_duplicates(inplace=True)
```python
5. Descriptive Statistics
```python
student_performance.describe()
student_performance.describe(include='object')
```
<img width="1771" height="739" alt="Screenshot 2026-04-27 221836" src="https://github.com/user-attachments/assets/0eae0c47-54c6-41e9-8210-788949e7c232" />

6. Univariate Analysis
```python
student_performance['final_score'].hist()
plt.title("Distribution of Final Scores")
plt.show()

sns.boxplot(x=student_performance['study_hours_per_week'])
plt.show()
```
<img width="780" height="589" alt="Screenshot 2026-04-27 221219" src="https://github.com/user-attachments/assets/589a6bc9-f2ff-4866-8771-ed5e36496205" />
<img width="787" height="650" alt="Screenshot 2026-04-27 221229" src="https://github.com/user-attachments/assets/7d00cc8c-673d-409c-8ae0-d0bdf1f87963" />

7. Categorical Features
```python
sns.countplot(x='gender', data=student_performance)
plt.show()
sns.countplot(x='passed', data=student_performance)
plt.show()
```
<img width="782" height="587" alt="Screenshot 2026-04-27 220952" src="https://github.com/user-attachments/assets/6758b9ea-e585-4e8f-814b-9277c25488e5" />
<img width="785" height="596" alt="Screenshot 2026-04-27 221003" src="https://github.com/user-attachments/assets/722d249e-cdd3-4a6b-822f-b96005833d19" />


8. Study Hours vs Final Score
```python
sns.scatterplot(x='study_hours_per_week', y='final_score', data=student_performance)
plt.show()
```
<img width="785" height="568" alt="Screenshot 2026-04-27 220920" src="https://github.com/user-attachments/assets/d956b98f-77c2-4eeb-b1e4-bb696848867c" />
```python
sns.relplot(x= 'final_score', y='study_hours_per_week', hue='gender', data=student_performance)
```
<img width="773" height="658" alt="Screenshot 2026-04-27 222415" src="https://github.com/user-attachments/assets/3500c2d4-8184-491f-9013-fc7bb5e86d20" />


9. Attendance vs Performance
```python
sns.scatterplot(x='attendance_rate', y='final_score', data=student_performance)
plt.show()
```
<img width="775" height="591" alt="Screenshot 2026-04-27 220747" src="https://github.com/user-attachments/assets/b8867d5a-0b75-40fc-b7d5-5c3dc7f4b510" />

10. Parent Education vs Scores
```python
sns.boxplot(x='parent_education', y='final_score', data=student_performance)
plt.show()
```
<img width="774" height="597" alt="Screenshot 2026-04-27 220433" src="https://github.com/user-attachments/assets/9f0855ea-e63b-413a-8f30-fb6eb902cd30" />

11. Internet Access Impact
```python
sns.boxplot(x='internet_access', y='final_score', data=student_performance)
plt.show()
```
<img width="774" height="597" alt="Screenshot 2026-04-27 220433" src="https://github.com/user-attachments/assets/2ed89250-7918-4cc3-a36d-ba0367b7ae7e" />
```python
sns.relplot(x= 'final_score', y='study_hours_per_week', hue='internet_access', data=student_performance)
```
<img width="931" height="740" alt="Screenshot 2026-04-27 222215" src="https://github.com/user-attachments/assets/2f5bf5f7-ccdf-4254-99d5-9f365d00949e" />

12. Correlation Heatmap
```python
corr = student_performance.corr(numeric_only=True)
sns.heatmap(corr, annot=True, cmap='coolwarm')
plt.show()
```
<img width="990" height="798" alt="Screenshot 2026-04-27 195548" src="https://github.com/user-attachments/assets/307b00be-ab62-4bcd-b4f9-18ecc99546cd" />

### Key Insights
* Students with higher study hours generally perform better academically
* Attendance rate shows a strong positive relationship with performance
* Previous academic scores are strong predictors of future outcomes
* Access to learning resources has a noticeable impact on performance
* Some inconsistencies suggest external factors may also influence results

### Recommendations

1. Focus on study habits and time management
Students with higher study hours per week and consistent attendance tend to perform better.
Recommendation: Schools should introduce structured study timetables and guided revision hours to improve consistency.

2. Improve attendance monitoring system
Low attendance is strongly linked to poor academic performance.
Recommendation: Implement early warning systems that flag students with declining attendance so interventions can be made early.

3. Parental involvement matters
Students with higher parental support or engagement show better outcomes.
Recommendation: Schools should create parent engagement programs (e.g., progress updates, parent-teacher dashboards).

4. Identify at-risk students early using data
Patterns in the data show that performance drops are predictable using features like study hours, attendance, and prior scores.
Recommendation: Schools can adopt basic predictive models to identify struggling students early.

5. Encourage balanced study behavior
Overstudying without breaks or consistency does not always improve performance.
Recommendation: Promote balanced learning schedules rather than cramming-based studying.

6. Use data-driven academic support
The analysis shows that student performance is not random but pattern-based.
Recommendation: Schools should integrate data analysis into academic planning for personalized student support.

Data Source 

[Download Here](https://github.com)

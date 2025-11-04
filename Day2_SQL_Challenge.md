📘 Day 2 – SQL With IDC Challenge

🗓 Challenge Task:
Find all patients admitted to the 'Surgery' service with a satisfaction score below 70, showing their patient_id, name, age, and satisfaction score.

💻 SQL Query:
SELECT patient_id, name, age, satisfaction
FROM patients
WHERE LOWER(service) = 'surgery'
  AND satisfaction < 70;

🧾 Output:
Displays all patients from the Surgery department whose satisfaction score is less than 70.
<img width="892" height="610" alt="Image" src="https://github.com/user-attachments/assets/75d41ecb-bbad-4a44-a156-14a589d2438e" />
<img width="477" height="314" alt="Image" src="https://github.com/user-attachments/assets/4ec5a1bd-d1dd-45ea-bbad-8b2da020ac7f" />

💡 Key Learnings:
* Operators:
    - Comparison: =, !=, <>, >, <, >=, <=
    - Logical: AND, OR, NOT
    - Pattern: LIKE, IN, BETWEEN
* Understood how to apply filters using the WHERE clause.
* Learned to use logical operators (AND, OR, NOT) for multiple conditions.
* Practiced using functions like LOWER() for case-insensitive matching.
* Observed how conditional queries help extract only relevant data from large datasets.

📂 Dataset:
The dataset used was patients.csv, containing patient details like service, satisfaction score, age, and more.

🧩 Summary:
This challenge improved understanding of data filtering and conditional selection in SQL.
I learned how to:
* Retrieve only the required rows using specific conditions.
* Combine conditions effectively using logical operators.
* Handle text-based filtering safely with functions like LOWER() or UPPER()

#SQLWithIDC #21DaysSQLChallenge #DataAnalytics #LearningJourney #DPDzero #IndianDataClub

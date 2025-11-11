📘 Day 8 – String Functions

🗓 Challenge Task:

Question: Create a patient summary that shows patient_id, full name in uppercase, service in lowercase, age category (if age >= 65 then 'Senior', if age >= 18 then 'Adult', else 'Minor'), and name length. Only show patients whose name length is greater than 10 characters.

💻 SQL Query:

SELECT patient_id, UPPER(name), LOWER(service), age, CASE WHEN age>=65 THEN 'Senior' WHEN age>=18 THEN 'Adult' ELSE 'Minor' END AS age_category, LENGTH(name) as name_length FROM patients WHERE LENGTH(name) > 10;

🧾 Output:

-Displays patient details with:

-Uppercase names

-Lowercase service

-Age category classification

-Only those whose name length exceeds 10
<img width="1280" height="591" alt="image" src="https://github.com/user-attachments/assets/eff452be-1827-4978-8cdd-6d5e6e6a9d06" />
922 rows selected

💡 Key Learnings:

Practiced string manipulation using UPPER(), LOWER(), LENGTH(), and CONCAT().

Learned to apply conditional logic with CASE statements.

Understood how to filter text data based on character count.

Improved readability of results by using column aliases.

📂 Dataset Used:
patients.csv – patient demographic, service, and satisfaction details.

🧩 Summary:
This challenge helped to explore how SQL string functions enhance data presentation and conditional formatting — useful for data cleaning and reporting.

#SQLWithIDC #21DaysSQLChallenge #DataAnalytics #LearningJourney #DPDzero #IndianDataClub

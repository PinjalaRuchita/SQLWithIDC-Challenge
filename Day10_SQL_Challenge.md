🗓️ Day 10 (13/11): CASE Statements

📘 Topics Covered:

CASE WHEN, conditional logic, derived columns

Daily Challenge:

Question: Create a service performance report showing service name, total patients admitted, and a performance category based on the following: 'Excellent' if avg satisfaction >= 85, 'Good' if >= 75, 'Fair' if >= 65, otherwise 'Needs Improvement'. Order by average satisfaction descending.

✅SQL Query:

SELECT
    service,
    SUM(patients_admitted) AS total_patients,
    ROUND(AVG(patient_satisfaction), 2) AS avg_satisfaction,
    CASE
        WHEN AVG(patient_satisfaction) >= 85 THEN 'Excellent'
        WHEN AVG(patient_satisfaction) >= 75 THEN 'Good'
        WHEN AVG(patient_satisfaction) >= 65 THEN 'Fair'
        ELSE 'Needs Improvement'
    END AS performance_category
FROM services_weekly
GROUP BY service
ORDER BY AVG(patient_satisfaction) DESC;

🪄 Output:

<img width="608" height="329" alt="image" src="https://github.com/user-attachments/assets/0f77775a-ee39-4e21-b112-45e6989b3d50" />


🧠 What I Learned:

The CASE statement adds conditional logic to SQL queries — similar to if-else in programming.

Two main types:

Simple CASE → compares one column to specific values.

Searched CASE → checks multiple conditions.

Useful for:

Categorizing data (like satisfaction or age group)

Performing conditional aggregation

Applying custom sorting logic

🚀 Reflection:

Learned to classify and analyze data using conditional logic.

CASE statements make SQL more dynamic and human-readable.

Perfect for building reports and dashboards.

#SQLWithIDC #DPDZero #LearnSQL #21DaysSQLChallenge #DataAnalytics #DatabaseLearning #indiandataclub

📅 Day 9 (12/11): Date Functions

💪 Daily Challenge

Question:Calculate the average length of stay (in days) for each service, showing only those services where the average stay is more than 7 days.
Also, show the count of patients and order by average stay (descending).

💻 SQL Query:

SELECT 
    service,
    COUNT(patient_id) AS total_patients,
    ROUND(AVG(JULIANDAY(departure_date) - JULIANDAY(arrival_date)), 2) AS avg_stay
FROM patients
WHERE departure_date IS NOT NULL
GROUP BY service
HAVING avg_stay > 7
ORDER BY avg_stay DESC;

📊 Output:

<img width="555" height="261" alt="image" src="https://github.com/user-attachments/assets/ee9bd5e7-b566-49ad-afbd-0c74956ea249" />


💡 Key Learnings

Learned how to handle and format dates in SQL.

Practiced calculating date differences for analytical use.

Applied aggregations with conditions (HAVING) on derived date data.

Improved understanding of data grouping and performance with date-based queries.

#SQLWithIDC #21DaysSQLChallenge #DPDzero #IndianDataClub #DataAnalytics #LearningJourney

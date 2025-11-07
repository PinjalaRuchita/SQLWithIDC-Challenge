📘 Day 5 – Aggregate Functions (COUNT, SUM, AVG, MIN, MAX)

🗓 Challenge Task:

Calculate the total number of patients admitted, total patients refused, and the average patient satisfaction across all services and weeks. Round the average satisfaction to 2 decimal places.

💻 SQL Query:

SELECT 
    SUM(patients_admitted) AS total_patients_admitted,
    SUM(patients_refused) AS total_patients_refused,
    ROUND(AVG(patient_satisfaction), 2) AS avg_satisfaction
FROM services_weekly;

🧾 Output:

Displays the overall hospital statistics across all services and weeks — total admissions, total refusals, and average satisfaction.
<img width="561" height="166" alt="Day5" src="https://github.com/user-attachments/assets/4bd1bbd5-346e-40a9-bf94-4658d7aa13f4" />


💡 Key Learnings:
- Understood how aggregate functions summarize large datasets.
  
-Learned to use:

  • SUM() → to calculate totals
  
  • AVG() → to find average values
  
  • ROUND() → to control decimal precision
- Realized the difference between COUNT(*) and COUNT(column).
  
- Observed that aggregate functions ignore NULL values (except COUNT(*)).

📂 Dataset Used:

services_weekly.csv – containing weekly service-level hospital data (admissions, refusals, satisfaction).

🧩 Summary:

This task strengthened understanding of aggregate analysis in SQL, helping summarize and interpret data efficiently — crucial for data analytics and reporting.

#SQLWithIDC #21DaysSQLChallenge #DataAnalytics #LearningJourney #DPDzero #IndianDataClub

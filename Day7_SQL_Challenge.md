## 📘 Day 7 – GROUP BY and HAVING Clauses

🗓 **Challenge Task:**
Identify services that refused more than 100 patients in total and had an average patient satisfaction below 80.
Show service name, total refused, and average satisfaction.

💻 **SQL Query:**

SELECT 
    service, 
    SUM(patients_refused) AS total_refused, 
    ROUND(AVG(patient_satisfaction), 2) AS avg_satisfaction
FROM services_weekly
GROUP BY service
HAVING SUM(patients_refused) > 100 
   AND AVG(patient_satisfaction) < 80;

🧾 **Output:**
Displays all hospital services where:

More than 100 patients were refused in total.

The average satisfaction score is below 80.
<img width="1349" height="146" alt="image" src="https://github.com/user-attachments/assets/c980191e-fa8c-471e-9f55-534de08a0374" />

💡 Key Learnings:

 Learned how to group data using GROUP BY for summary-level analysis.

 Understood how HAVING filters groups (like WHERE but used after aggregation).

 Practiced combining aggregate functions with conditional filtering.

 Used ROUND() for cleaner, formatted averages.

📂Dataset Used:

services_weekly.csv – weekly hospital service data with metrics like admissions, refusals, and satisfaction scores.

🧩 Summary:

This challenge helped in understanding how to derive **insights from grouped data**, such as identifying underperforming services based on refusals and satisfaction. It strengthens analytical thinking with SQL.

#SQLWithIDC #21DaysSQLChallenge #DataAnalytics #LearningJourney #DPDzero #IndianDataClub

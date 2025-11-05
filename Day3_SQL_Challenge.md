📘 Day 3 – Sorting Data with ORDER BY

🗓 Challenge Task:
Retrieve the top 5 weeks with the highest patient refusals across all services, showing week, service, patients_refused, and patients_request.
Sort the results by patients_refused in descending order.

💻 SQL Query:
SELECT week,
       service,
       patients_refused,
       patients_request
FROM services_weekly
ORDER BY patients_refused DESC
FETCH FIRST 5 ROWS ONLY;

🧾 Output:
Displays the top 5 records with the highest number of patient refusals.
<img width="1205" height="183" alt="DAY3" src="https://github.com/user-attachments/assets/5d1f3908-af0d-4526-91e4-6ff37311ea72" />

💡 Key Learnings:
* Learned to use the ORDER BY clause to sort records in descending order.
* Practiced using FETCH FIRST n ROWS ONLY / LIMIT to extract top results.
* Understood how to compare and analyze multiple metrics (patients_refused vs. patients_request).
* Strengthened skills in writing ranking and sorting queries.

📂 Dataset:
* services_weekly.csv — contains weekly statistics for different hospital services.

🧩 Summary:
* This challenge helped in understanding how to rank data based on specific columns and extract the most significant entries using SQL’s sorting and limiting features.
* It is an essential technique for data analysis and decision making in real-world datasets.

#SQLWithIDC #21DaysSQLChallenge #DataAnalytics #LearningJourney #IndianDataClub #DPDZero

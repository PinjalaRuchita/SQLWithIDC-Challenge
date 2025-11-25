📘 Day 19 – SQL With IDC Challenge

Window Functions – ROW_NUMBER(), RANK(), DENSE_RANK()

Daily Challenge:

Question: For each service, rank the weeks by patient satisfaction score (highest first). Show service, week, patient_satisfaction, patients_admitted, and the rank. Include only the top 3 weeks per service.

SQL Query:

WITH ranked AS (
  SELECT
    service,
    week,
    patient_satisfaction,
    patients_admitted,
    ROW_NUMBER() OVER (
      PARTITION BY service
      ORDER BY patient_satisfaction DESC
    ) AS rn
  FROM services_weekly
)
SELECT service, week, patient_satisfaction, patients_admitted, rn
FROM ranked
WHERE rn <= 3
ORDER BY service, rn;

🧾Output:

<img width="1340" height="630" alt="image" src="https://github.com/user-attachments/assets/c28814d0-74d5-4ff6-8b9e-6da2184a38d6" />

 💡 Key Learnings

Understood how window functions work in SQL

Learned differences between ROW_NUMBER, RANK, and DENSE_RANK

Practiced ranking data without collapsing rows

Explored PARTITION BY to group calculations

Saw how to filter window results using subqueries

🧩 Summary

Today’s challenge improved understanding of:

Window functions and their real-world usage

Ranking and ordering within groups

Filtering window results using a wrapper query

Insights from **weekly health service performance**

This is a powerful technique for analytics dashboards, reporting, and performance insights.

#SQLWithIDC #21DaysSQLChallenge #DataAnalytics #LearningJourney #DPDzero #IndianDataClub

📘 Day 15 – SQL With IDC Challenge

🗓 Topic: Multiple Joins

Multiple JOINs help combine three or more tables to form meaningful analytical reports. This is widely used in real-world datasets where information is spread across different tables.

Daily Challenge:

Question: Create a comprehensive service analysis report for week 20 showing: service name, total patients admitted that week, total patients refused, average patient satisfaction, count of staff assigned to service, and count of staff present that week. Order by patients admitted descending.

SQLQuery:

SELECT
  sw.service,
  sw.patients_admitted,
  sw.patients_refused,
  sw.patient_satisfaction        AS avg_patient_satisfaction,
  COUNT(DISTINCT s.staff_id)     AS total_staff_assigned,
  SUM(CASE WHEN ss.present = 1 THEN 1 ELSE 0 END) AS staff_present_count
FROM services_weekly sw
LEFT JOIN staff s
  ON sw.service = s.service
LEFT JOIN staff_schedule ss
  ON s.staff_id = ss.staff_id
  AND ss.week = sw.week
WHERE sw.week = 20
GROUP BY
  sw.service,
  sw.patients_admitted,
  sw.patients_refused,
  sw.patient_satisfaction
ORDER BY sw.patients_admitted DESC;

OUTPUT:

 <img width="1280" height="460" alt="image" src="https://github.com/user-attachments/assets/1b665083-67e9-4758-b7a5-2bb89d1c45e5" />

🔍 What I Learned Today

How JOINs work when connecting 3 or more tables

How JOIN order affects output

How to mix INNER JOIN + LEFT JOIN in one query

How to avoid duplicates using DISTINCT / GROUP BY

How to join tables using conditions from previously joined tables

How to break complex queries into simple steps

🧩 Summary

Today’s challenge helped me understand how to:

Connect multiple tables together

Build complex analytical queries

Apply LEFT JOIN + INNER JOIN combinations

Interpret multi-table data in real-world healthcare scenarios

#SQLWithIDC #21DaysSQLChallenge #DataAnalytics #LearningJourney #DPDzero #IndianDataClub

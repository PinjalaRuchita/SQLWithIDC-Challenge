📘 Day 21 – SQL With IDC Challenge

Daily Challenge:

Question: Create a comprehensive hospital performance dashboard using CTEs. Calculate: 1) Service-level metrics (total admissions, refusals, avg satisfaction), 2) Staff metrics per service (total staff, avg weeks present), 3) Patient demographics per service (avg age, count). Then combine all three CTEs to create a final report showing service name, all calculated metrics, and an overall performance score (weighted average of admission rate and satisfaction). Order by performance score descending.

SQL Query:

WITH
service_level AS (
    SELECT
        service,
        SUM(patients_admitted) AS total_admissions,
        SUM(patients_refused)  AS total_refusals,
        AVG(patient_satisfaction) AS avg_satisfaction,
        SUM(patients_request) AS total_requests,
        CASE
            WHEN SUM(patients_request) > 0 THEN
                SUM(patients_admitted) / SUM(patients_request)
            ELSE 0
        END AS admission_rate
    FROM services_weekly
    GROUP BY service
),
staff_metrics AS (
    SELECT
        s.service,
        COUNT(DISTINCT s.staff_id) AS total_staff,
        CASE 
            WHEN COUNT(DISTINCT s.staff_id) > 0 THEN
                COUNT(DISTINCT sw.week) / COUNT(DISTINCT s.staff_id)
            ELSE 0
        END AS avg_weeks_present
    FROM staff s
    LEFT JOIN services_weekly sw
        ON s.service = sw.service
    GROUP BY s.service
),
patient_demo AS (
    SELECT
        service,
        AVG(age) AS avg_age,
        COUNT(*) AS patient_count
    FROM patients
    GROUP BY service
)
SELECT
    sl.service AS service_name,
    sl.total_admissions,
    sl.total_refusals,
    sl.total_requests,
    sl.admission_rate,
    sl.avg_satisfaction,
    sm.total_staff,
    sm.avg_weeks_present,
    pd.avg_age,
    pd.patient_count,
    (
        0.7 * (sl.admission_rate * 100) +
        0.3 * sl.avg_satisfaction
    ) AS performance_score
FROM service_level sl
LEFT JOIN staff_metrics sm
    ON sl.service = sm.service
LEFT JOIN patient_demo pd
    ON sl.service = pd.service
ORDER BY performance_score DESC;

 🧾 Output

<img width="1280" height="186" alt="image" src="https://github.com/user-attachments/assets/d59fa25c-6d95-44cc-9634-5725e6167033" />

💡 Key Learnings

Learned how to use the WITH clause to structure complex queries

Understood how multiple CTEs can work together

Combined data from patients, staff, staff_schedule, and services_weekly

Built a dashboard-style analytical report

Applied weighted calculations for performance scoring

Improved query readability and maintainability

🧩 Summary

This challenge helped me understand how CTEs simplify complex SQL analysis by breaking queries into logical steps. I successfully designed a hospital performance dashboard by integrating multiple datasets and applying real-world analytical metrics using structured SQL.

#SQLWithIDC #Day21 #AdvancedSQL #DataAnalytics #LearningJourney #DPDzero #IndianDataClub


📘 Day 17 – SQL With IDC Challenge

🗓 Subqueries in SELECT & FROM Clause (22/11)

Daily Challenge:

Question: Create a report showing each service with: service name, total patients admitted, the difference between their total admissions and the average admissions across all services, and a rank indicator ('Above Average', 'Average', 'Below Average'). Order by total patients admitted descending.

SQL Query:

SELECT
    service,
    total_admitted,
    total_admitted - overall_avg AS diff_from_avg,
    CASE
        WHEN total_admitted > overall_avg THEN 'Above Average'
        WHEN total_admitted = overall_avg THEN 'Average'
        ELSE 'Below Average'
    END AS performance
FROM (
    SELECT
        service,
        SUM(patients_admitted) AS total_admitted
    FROM services_weekly
    GROUP BY service
) service_totals,
(
    SELECT
        AVG(total_admitted) AS overall_avg
    FROM (
        SELECT SUM(patients_admitted) AS total_admitted
        FROM services_weekly
        GROUP BY service
    )
)
ORDER BY total_admitted DESC;


OUTPUT:

<img width="1175" height="545" alt="image" src="https://github.com/user-attachments/assets/271c98c2-67d0-4b37-af45-46cb5546d23e" />


🔍 What I Learned Today

-Subqueries in SELECT

These return one calculated value per row, such as averages, counts, totals, or comparisons.

-Subqueries in FROM (Derived Tables)

These behave like temporary tables created inside your query.

Tips & Tricks

Always alias derived tables

Subqueries in SELECT must return a single value

Correlated subqueries run once per row

Derived tables help break down complex logic

🧩 Summary

Today strengthened understanding of:

Inline subqueries

Derived tables

Inline calculations

Designing multi-step SQL queries

Analytical thinking for real-world hospital data

#SQLWithIDC #LearningJourney #21DaysSQLChallenge #DPDzero #IndianDataClub

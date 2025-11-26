Day 20: Window Functions – Aggregate Window Functions

Daily Challenge:

Question: Create a trend analysis showing for each service and week: week number, patients_admitted, running total of patients admitted (cumulative), 3-week moving average of patient satisfaction (current week and 2 prior weeks), and the difference between current week admissions and the service average. Filter for weeks 10-20 only.

SQL QUERY:

SELECT
  service,
  week,
  patients_admitted,
  SUM(patients_admitted) OVER (PARTITION BY service ORDER BY week
      ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS running_total,
  ROUND(AVG(patient_satisfaction) OVER (PARTITION BY service ORDER BY week
      ROWS BETWEEN 2 PRECEDING AND CURRENT ROW),2) AS moving_avg_3_weeks,
  patients_admitted - AVG(patients_admitted) OVER (PARTITION BY service) AS diff_from_service_avg
FROM services_weekly
WHERE week BETWEEN 10 AND 20
ORDER BY service, week;

OUTPUT:

<img width="757" height="682" alt="image" src="https://github.com/user-attachments/assets/28acfb0d-45c2-46b7-8e3c-605ab9677110" />

Topics

SUM() OVER, AVG() OVER, running totals, moving averages

Window functions allow calculating running totals, moving averages, and cumulative metrics without collapsing rows.

Common window aggregates: running totals, moving averages, running counts, cumulative min/max.

Window frame options include:

UNBOUNDED PRECEDING, N PRECEDING, CURRENT ROW, N FOLLOWING, UNBOUNDED FOLLOWING.

Key Ideas:

Using ORDER BY inside OVER creates a default frame from the first row to the current row.

Without ORDER BY, the window frame is the full partition.

Moving averages use ROWS BETWEEN.

You can calculate differences from window aggregates (e.g., deviation from average).

Window functions cannot be nested, but you can have multiple in the same SELECT.

Summary:

Day 20 focused on aggregate window functions like running totals, moving averages, cumulative statistics, and comparisons to group averages. We learned how ORDER BY and window frames shape results, how to use ROWS BETWEEN for moving calculations, and how window functions help analyze trends without losing row-level detail.

#SQLWithIDC #21DaysSQLChallenge #WindowFunctions #SQLAnalytics #LearningJourney #DataAnalytics #DPDzero #IndianDataClub

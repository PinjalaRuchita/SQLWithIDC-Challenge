📘 Day 18 – SQL With IDC Challenge

🗓 Topic: UNION and UNION ALL — combining result sets

Daily Challenge:

Question: Create a comprehensive personnel and patient list showing: identifier (patient_id or staff_id), full name, type ('Patient' or 'Staff'), and associated service. Include only those in 'surgery' or 'emergency' services. Order by type, then service, then name.

SQL Query:

SELECT 
    identifier,
    full_name,
    person_type,
    service
FROM (
    SELECT 
        patient_id AS identifier,
        name AS full_name,
        'Patient' AS person_type,
        service
    FROM patients
    WHERE LOWER(service) IN ('surgery', 'emergency')
    UNION ALL
    SELECT 
        staff_id AS identifier,
        staff_name AS full_name,
        'Staff' AS person_type,
        service
    FROM staff
    WHERE LOWER(service) IN ('surgery', 'emergency')
)
ORDER BY 
    person_type,
    service,
    full_name;
    
OUTPUT:

<img width="1280" height="656" alt="image" src="https://github.com/user-attachments/assets/3ef8092f-3078-46a7-9f93-5cb550cffaf2" />

✅ Key points

Columns count and types must match across the SELECTs.

Column names come from the first SELECT.

Use UNION ALL when you want to preserve duplicates and for performance.

Use literals to identify the source table (e.g., 'Patient', 'Staff').

🔎 Summary

UNION combines results from multiple SELECT statements into a single result set and removes duplicate rows.

UNION ALL combines results as well but keeps duplicates (faster).

#SQLWithIDC #LearningJourney #21DaysSQLChallenge #DPDzero #IndianDataClub

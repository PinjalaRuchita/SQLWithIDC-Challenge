📅 Day 12 (15/11): NULL Values and IS NULL / IS NOT NULL

Topics:

Handling NULL, using IS NULL, IS NOT NULL, COALESCE

🎯 Daily Challenge (Day 12)

Question: Analyze the event impact by comparing weeks with events vs weeks without events. Show: event status ('With Event' or 'No Event'), count of weeks, average patient satisfaction, and average staff morale. Order by average patient satisfaction descending.

SQL Query:

select case when lower(trim(event)) = 'none' or event is NULL THEN 'No Event'
else 'With Event' end as event_count,
count(distinct week) as week_count,
round(avg(patient_satisfaction),2) as average_satisfaction,
round(avg(staff_morale),2) as average_morale
from services_weekly
group  by
case when lower(trim(event)) = 'none' or event is NULL THEN 'No Event'
else 'With Event' end
order by
round(avg(patient_satisfaction),2) desc;

Output:

<img width="1061" height="405" alt="image" src="https://github.com/user-attachments/assets/abb76022-c6d6-427d-9a2e-edf2abd60235" />

Learning Outcomes:

Learned what NULL means in SQL.

Practiced using IS NULL and IS NOT NULL.

Used COALESCE() to replace NULL values.

Understood how NULL affects COUNT and calculations.

Analyzed data with and without events.

Summary

Today I learned how to handle NULL values in SQL. I practiced checking NULLs, replacing them using COALESCE, and understanding how NULL affects queries. I also compared weeks with events vs no events to see their impact on satisfaction and morale.

#SQLWithIDC #Day12 #SQL #NullValues #LearningSQL #IndianDataClub


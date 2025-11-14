📅 Day 11 (14/11): DISTINCT and Handling Duplicates

📘 Topics:

DISTINCT, removing duplicates, unique values

Daily Challenge:

Question:Find all unique combinations of service and event type from the services_weekly table where events are not null or none, along with the count of occurrences for each combination. Order by count descending.

SQL Query:

select distinct service, event, count(service) as count
  from services_weekly
  group by service, event
  order by count(service) desc;
  
Output:

<img width="1280" height="508" alt="image" src="https://github.com/user-attachments/assets/6c5d6e87-a99e-4e1c-ac1d-2827570e9977" />

📖 Concept Summary

The DISTINCT keyword removes duplicate rows from your result set and returns only unique values or unique combinations.

🔍 Key Concepts

DISTINCT considers all selected columns together

Works like “unique combinations”

Can affect performance on large tables

#SQLWithIDC #DPDZero #LearnSQL #21DaysSQLChallenge #DataAnalytics #DatabaseLearning #indiandataclub

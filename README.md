# Google Capstone Project

Contents

This repository was created to store files associated with the project titled, Google Capstone Project. 
The project relates to Bellabeat's(a smart device company). Urška Sršen, cofounder and Chief Creative Officer of Bellabeat would like more insight into how consumers use their smart devices to guide Bellabeat's marketing strategy. She believes that analyzing smart device fitness data could help unlock new growth opportunities for the company. 
The documents above include:

- the process I followed from start to finish
- details about the objectives of the report and; analaysis and results using SQL, R and Tableau
2. SQL Queries - Includes analysis done using SQL. 
3. R Queries - Includes analysis using R. 
4. Excel Files - The data used for this project. 
![Bellabeat](https://user-images.githubusercontent.com/91411766/151315777-8633641b-ca25-42fa-a38f-7f3928c78497.JPG)

SELECT 
  CAST(AVG(SedentaryMinutes) AS INT) AS Sedentary_Minutes,
  CAST(AVG(LightlyActiveMinutes) AS INT) AS Lightly_Active_Minutes,
  CAST(AVG(FairlyActiveMinutes) AS INT) AS Fairly_Active_Minutes,
  CAST(AVG(VeryActiveMinutes) AS INT) AS Very_Active_Minutes,
  CAST(AVG(SedentaryMinutes) + AVG(LightlyActiveMinutes) + AVG(FairlyActiveMinutes) + AVG(VeryActiveMinutes) AS INT) AS Total_Minutes
  
  FROM capstone-project-338712.Daily_Activity.Activity_Summary AS Activity_Summary

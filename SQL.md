-- How many Fitbit users participated?

```
SELECT 
  COUNT(Distinct Id) AS Number_of_Participants
FROM `capstone-project-338712.Daily_Activity.Activity_Summary`
```


-- How long were users active and how long were they sedentary?

```
SELECT 
  CAST(AVG(SedentaryMinutes) AS INT) AS Sedentary_Minutes,
  CAST(AVG(LightlyActiveMinutes) AS INT) AS Lightly_Active_Minutes,
  CAST(AVG(FairlyActiveMinutes) AS INT) AS Fairly_Active_Minutes,
  CAST(AVG(VeryActiveMinutes) AS INT) AS Very_Active_Minutes,
  CAST(AVG(SedentaryMinutes) + AVG(LightlyActiveMinutes) + AVG(FairlyActiveMinutes) + AVG(VeryActiveMinutes) AS INT) AS Total_Minutes
  
FROM capstone-project-338712.Daily_Activity.Activity_Summary AS Activity_Summary
```
  

-- What is the average BMI of each participant that have BMI data?

```
SELECT  
  Id,
  CAST( AVG(BMI) AS INT) AS Average_BMI
FROM `capstone-project-338712.Daily_Activity.Weight_Data`
  GROUP BY Id  
```


-- Is there a relationship between users average sleep minutes and their average total steps?

```
SELECT  
  Activity_Summary.Id,
  CAST(AVG(TotalSteps) AS INT) AS Avg_Total_Steps,
  CAST (AVG(TotalMinutesAsleep) AS INT) AS Avg_Sleep_Minutes
FROM capstone-project-338712.Daily_Activity.Activity_Summary AS Activity_Summary
 JOIN capstone-project-338712.Daily_Activity.Sleep_Data AS Sleep_Data ON
      Activity_Summary.Id = Sleep_Data.Id
 GROUP BY Id
 ORDER BY Avg_Sleep_Minutes
 ```
 

-- Identifying if users were underweight, ideal weight or overweight according to their BMI each day.

```
SELECT
 Id,
 Date,
 WeightKg,
 BMI,
 
 CASE 
 WHEN BMI < 18 THEN 'Underweight'
 WHEN BMI Between 18 AND 25 THEN 'Ideal'
 WHEN BMI > 25 THEN 'Overweight'
 ELSE ""
 END AS Result
FROM capstone-project-338712.Daily_Activity.Weight_Data AS Weight_Data
```


-- Identify days when overweight users were very active, walked more than 3000 steps and slept less than 7 hours.

```
SELECT 
  Activity_Summary.Id,
  ActivityDate AS Activity_Date,
  VeryActiveMinutes AS Very_Active_Minutes,
  TotalSteps AS Total_Steps,
  BMI AS Body_Mass_Index,
  TotalMinutesAsleep AS Sleep_Minutes,
  
FROM capstone-project-338712.Daily_Activity.Activity_Summary AS Activity_Summary
 JOIN capstone-project-338712.Daily_Activity.Weight_Data AS Weight_Data ON
     Activity_Summary.Id = Weight_Data.Id
 JOIN capstone-project-338712.Daily_Activity.Sleep_Data AS Sleep_Data ON     
     Activity_Summary.Id = Sleep_Data.Id  
WHERE BMI >= 25 
 AND VeryActiveMinutes > 0
 AND TotalMinutesAsleep <= 420
 AND TotalSteps > 3000
 ORDER BY Very_Active_Minutes
```


-- Identify days when users slept more than 7 hours and walked more than 3000 steps.

```
SELECT 
  Activity_Summary.Id,
  Date,
  TotalSteps AS Total_Steps,
  TotalMinutesAsleep AS Sleep_Minutes,
  TotalTimeInBed AS Time_in_Bed
  
FROM capstone-project-338712.Daily_Activity.Activity_Summary AS Activity_Summary
 JOIN capstone-project-338712.Daily_Activity.Sleep_Data AS Sleep_Data ON     
     Activity_Summary.Id = Sleep_Data.Id  
WHERE TotalMinutesAsleep > 420
  AND TotalSteps > 3000
```


-- How long were users who walked less than 5000 steps, sedentary but were also very active during the day. 

```
SELECT 
 Id, 
 ActivityDate,
 VeryActiveMinutes,
 SedentaryMinutes,
FROM `capstone-project-338712.Daily_Activity.Activity_Summary` 
WHERE TotalSteps < 5000
AND VeryActiveMinutes > 1
ORDER BY SedentaryMinutes DESC
```


-- Identify the hour of the day that each participant burnt the most calories. 

```
SELECT *
FROM capstone-project-338712.Daily_Activity.Hourly_Calories
WHERE CONCAT(Id, Date, Calories) IN 
  (SELECT 
    CONCAT(Id, Date, Max(Calories))
   FROM capstone-project-338712.Daily_Activity.Hourly_Calories
    GROUP BY Id, Date) 
 ORDER BY Id, Date, Calories 
```

# Project Files Guide and Narration of Objectives and Findings
## *In the documents above you will find:*
1. Excel Files - The data used for this project. 
2. Process - A summary of the steps I took to complete this project from start to finish.
3. R Queries - Analysis using R.
4. README - The file you are presently reading which includes a narrative of the project objectives and findings.
5. SQL Queries - Analysis using SQL. 

## *Below you will find a narrative including details about the objectives of the report and; analysis and results using SQL, R and Tableau:*

<img src="https://user-images.githubusercontent.com/91411766/151370034-ea4340e1-0844-4dee-bbdc-c9c3fc2aeb24.JPG" width="500" height="500">

# Inspiration
1.	Did participants who were very active walk at least 5000 steps a day?
2.	How long were participants active and how long were they sedentary each day?
3.	What is the average BMI level of each participant?
4.	Did users sleep at least 7 hours each day?
5.	What are some trends in smart device usage?
6.	How could these trends apply to Bellabeat's customers?
7.	How could these trends help influence Bellabeat marketing strategy?


# Contents
1.	Executive Summary
2.	Introduction
3.	Data Used for Analysis
4.	Findings
5.	Recommendations
6.	Further Research
7.	Reference List

# Executive Summary
The purpose of this analysis is to analyze how people use their Fitbit smart devices to find opportunities for growth and provide recommendations to guide Bellabeat’s marketing strategy.  
After cleaning, and analyzing the data, I found that most smart watch users are active for only a few hours a day. This may indicate that most consumers of smart watches are not blue-collar workers. 
Additionally, half of the participants (four out of eight) that provided BMI data were overweight and half (twelve out of twenty four) slept less than the recommended seven hours (How much sleep do I need?, 2019).  
However, most users walked more than the recommended 5000 steps a day which is considered necessary as shown in a study done by the University of Texas (Lindsay Bottoms, The Conversation, 2021). 
Bellabeat can focus their marketing strategy on showing how their Time watch caters to the individual needs of customers by providing them with suggestions to help them maintain a healthy body since most people buy smart watches without displays to track health related metrics.  

# Introduction

Urška Sršen, cofounder and Chief Creative Officer of Bellabeat's(a smart device company)  would like more insight into how consumers use their smart devices to guide Bellabeat's marketing strategy. She believes that analyzing smart device fitness data could help unlock new growth opportunities for the company. 

The Time watch by Bellabeat’s is the product I chose to focus on. People who purchase this watch receive 3 months of exercising and meditating with the Bellabeat Wellness Coach. This usually costs $9.99 a month. The Time watch works with an APP. It helps people monitor their health to achieve total body wellness. 
It gives people insight into their daily lifestyle by providing metrics to help inform their dietary and activity decisions. 
The Time watch is focused on women and provides menstrual cycle support through tracking metrics and providing users with information via the APP about each stage of their menstruation cycle. 
Together, the Time watch and the APP have features such as monitoring stress and offers yoga routines and meditation to help manage stress levels. 
In addition, personalized exercise routines and meal plans are also provided, and the Time watch helps monitor calories burned each day and compares it to the amount of food consumed to manage weight and BMI levels. 

# Data Used for Analysis

Urška Sršen has directed me to a dataset (about thirty three Fitbit smart device users who participated in a study) called FitBit Fitness Tracker Data that was made available through Mobius and which I downloaded from the Kaggle website.

Some limitations and assumptions of the data provided:

1.	The dataset included just 33 participants for activity. 24 users provided information about sleep, 8 users provided information about their BMI levels and just 7 had heart rate data. 
2.	It is unknown whether participants are male or female and Bellabeat’s focuses on female customers. 
3.	The time zone was not provided. I assumed that it was given according to each user’s location eg. 12:00 is midday in their location. 
4.	The criteria that differentiate intensity is unknown. 
5.	Participants ages were not provided and so their recommended caloric needs and recommended heart rate range could not be calculated (What heart rate is too high? Is 200 bpm bad? Chart, no date).
6.	Distance metrics are unknown. I assumed kilometers. 

The metadata shows that the data was created on the 16th of December 2020. However, there hasn’t been any significant updates to smart watches since then which makes this data current. From my research it appears that people buy smart watches mostly to monitor their activity and the most promising future use that I came across would be for smart watches to help identify when people need medical care. While smart watches can monitor metrics like heart rates and indicate when a user’s heart rate may be too low, medical care features are still in its infancy stage as the smart device would also need to check other health metrics such as blood pressure to be more useful. Additionally, use for health care decisions will require evaluation of these devices for that purpose by the relevant authorities in each country. 

# Findings

Thirty-three participants provided activity data. I found that the average activity time was 193 minutes or less each day for participants. Additionally, users were mostly lightly active with the average fairly active minutes and very active minutes being 14 and 21 minutes, respectively. 

Only eight of the thirty-three users provided data on BMI levels. I found that four of these users were overweight as their BMI levels were over 25. 

Twenty-four users provided data about sleep. Twelve of these users slept less than 7 hours and may end up with cardiovascular disease, diabetes as well as increased ghrelin levels and decreased leptin levels which result in a lack of appetite control (Can overeating cause sleep disturbances?, 2020). 
Even though these users slept less than 7 hours, most still walked more than the 5000 steps a day which is recommended to metabolize fat and prevent many health-related problems (Lindsay Bottoms, The Conversation, 2021).  


![Fitbit user Analysis Dashboard](https://user-images.githubusercontent.com/91411766/151371093-6e420d62-7a6e-4e3a-85e2-8b3277967218.JPG)


I also found that most users who were very active for just a few minutes each day walked more than 5000 steps. 


![VeryActiveUsersSteps](https://user-images.githubusercontent.com/91411766/151495639-314e6ac8-3c2f-4494-9874-0b3f2e617ecd.png)

# Recommendations

Assuming a client logs their daily diet manually the Time watch can be used in conjunction with the Bellabeat App to track their daily calorie needs and provide suggestions of foods with the nutrition that the client lacks for the day or should be eaten or avoided due to menstruation. (Which foods to eat and avoid during your period, no date). 

The Time watch offers people the ability to stay in optimal health by tracking heart rates which offer insight into when people should consult a doctor eg. if they have a high or low resting heart rate (Bradycardia, no date).
For example, if your heart rate is higher than normal in the morning it could be a sign of impending an impending cold or flu. An increase in your resting heart rate over time may be a sign of future heart trouble.

Additionally, if people input their weight and height into the Bellabeat App, their BMI can be calculated, and the Time watch can help them (by tracking data such as calories burned) move towards or stay in the recommended BMI ranges of a healthy adult. 

Clients should be made more aware of the benefits of tracking metrics like nutrition, heart rates and BMI levels. Marketing strategies should focus on these benefits. The APP can be upgraded to provide more personalized suggestions for not just exercise routines and meals plans but also for snacks with nutrition that a user may be lacking for the day or require during menstruation, adjusting calories during menstruation when customers are likely to be less active or seeing a doctor due to an irregular heart rate. Data about the hour when each user was the most active each day was identified in my analysis. If a pattern exists for individual users, Bellabeat could use this data to communicate with clients around this time by sending them appropriate notifications such as healthy snack suggestion as they are likely to reach for a snack after their most active hour.    

In conclusion, Bellabeat can focus their marketing strategy on showing people how their Time watch helps individuals and does not take a one size fits all approach when providing clients with information.

# Further Research

1. I would redo the analysis with a much larger sample and compare its results with the results from this study to check for consistency.

2. I would search for country with increasing growth in GDP and identify whether people are sleeping less and working more due to higher levels of economic activity. I would then research whether these countries are also experiencing increasing obesity levels and more generally if people are eating more than they should. This could identify new target markets for a product like Bellabeat’s Time watch as people in these countries are likely to have an increasing disposable income.  


# Reference List

1.	Lindsay Bottoms, The Conversation (2021) Fitness watch: Ten thousand steps a day is great but even half the number will do the trick, Scroll.in. Available at: https://scroll.in/field/985499/fitness-watch-ten-thousand-steps-a-day-is-great-but-even-half-the-number-will-do-the-trick (Accessed: January 27, 2022).

2.	Lww.com. Available at: https://journals.lww.com/acsm-msse/Fulltext/2021/02000/Daily_Step_Count_and_Postprandial_Fat_Metabolism.10.aspx (Accessed: January 27, 2022).

3.	(How much sleep do I need?, 2019)
How much sleep do I need? (2019) Cdc.gov. Available at: https://www.cdc.gov/sleep/about_sleep/how_much_sleep.html (Accessed: January 27, 2022).

4.	(Bradycardia, no date)
Bradycardia (no date) Cedars-Sinai. Available at: https://www.cedars-sinai.org/health-library/diseases-and-conditions/b/bradycardia.html (Accessed: January 28, 2022).

5.	Which foods to eat and avoid during your period (no date) Flo.health - #1 mobile product for women’s health. Available at: https://flo.health/menstrual-cycle/lifestyle/diet-and-nutrition/foods-to-eat-on-period (Accessed: January 28, 2022).

6.	(What heart rate is too high? Is 200 bpm bad? Chart, no date)
What heart rate is too high? Is 200 bpm bad? Chart (no date) MedicineNet. Available at: https://www.medicinenet.com/what_heart_rate_is_too_high/article.htm (Accessed: January 28, 2022).

7.	Can overeating cause sleep disturbances? (2020) Sleep Foundation. Available at: https://www.sleepfoundation.org/physical-health/sleep-and-overeating (Accessed: January 28, 2022)



























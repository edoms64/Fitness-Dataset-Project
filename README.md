# Fitness-Dataset-Project
This project is an analysis of the dataset of a fitness studio &amp; insights generated from the data in the database. This database represents a fitness platform that manages members (users), trainers, fitness classes, membership plans (subscriptions), and the workouts logged by members. These tables display the full lifecycle of member engagement.

SQL Code for Fitness Dataset Project

1. Which class difficulty levels are the most highly utilized?

The class difficulty levels that are the most highly utilized are, in order, “advanced” ranking first with 242,130 users. Coming in second place is “intermediate” class difficulty level with 216,211 users. In last place, it is “beginner” class difficulty level with 157,764 users. With this breakdown, “advanced” is the most highly utilized class difficulty level. This SQL query was created by first selecting columns from the ‘classes’ table and changing the names of said columns in order to make them more distinct. The sum of user id’s and naming that sum as ‘Total Number of Users’ was also implemented in the ‘SELECT’ step. Then, the next step was to do a left join ‘workouts’ table into the ‘classes’ table utilizing ‘class_id’. Then, the next step is to group by the difficulty level of classes. The final step is to order by total number of users in descending order.

SQL Query:

SELECT

classes.class_id AS "Class ID",

classes.difficulty_level AS "Difficulty Level",

SUM(user_id) AS "Total Number of Users"

FROM classes

LEFT JOIN workouts ON classes.class_id = workouts.class_id

GROUP BY classes.difficulty_level

ORDER BY "Total Number of Users" DESC;

Results:


<img width="626" height="122" alt="Screenshot 2026-01-10 at 3 29 07 AM" src="https://github.com/user-attachments/assets/ce714e58-7815-46e3-a247-47d1c9be2bab" />


2.  How do weekly calorie totals trend over time for each user?

Displayed below are results (a snapshot of the results) of weekly calorie totals trending over time for several users. In this snapshot, there is an upward and downward trend (increase and decrease of calories burned) weekly, seemingly dependent on the duration of minutes of each workout. When a user (ex. User_ID = 400) spends more minutes working out, the calories burned per week increases and when a user spends less time working out, the calories burned per week decreases.  This SQL query was created by first selecting columns from the ‘workouts’ table and changing the names of said columns in order to make them more distinct. Then, the rows were ordered by “User_ID” DESC and “Workout Date and Time” to show the range of workout dates and times per user together in a descending order.

SQL Query:

SELECT
workouts.user_id AS "User_ID",
workouts.workout_datetime AS "Workout Date and Time",
workouts.duration_minutes AS "Duration of Minutes",
workouts.calories_burned AS "Calories Burned"
FROM workouts
ORDER BY "User_ID" DESC, "Workout Date and Time";

Results:

<img width="595" height="291" alt="Screenshot 2026-01-10 at 3 39 14 AM" src="https://github.com/user-attachments/assets/10912653-eb6e-4e29-aec9-ed403bae6dc0" />


Machine Learning Model and Data Visualizations for Fitness App Poroject

[Linear_Regression_and_Random_Forest_Model (1).ipynb](https://github.com/user-attachments/files/24988569/Linear_Regression_and_Random_Forest_Model.1.ipynb)


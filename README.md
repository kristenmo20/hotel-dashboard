# hotel-dashboard
Dashboard for hotel management to track revenue and cancellation rates by month

## Goal:
Develop a Database to Analyze & Visualize Hotel Booking Data

## Requirements
Build a visual data story or dashboard using Power BI to present to your stakeholders.

Question posed by stakeholders
"Is our hotel revenue growing by year?"
"Which months have the highest cancellations?

Data Analysis Project Pipeline
1. Build a Database
2. Develop the SQL
3. Connect Power BI to the Database
4. Visualize
5. Summarize Findings
  
### Building the database

The tables necessary for analysis were combined into a temp table using the WITH and UNION SQL Statements

The dataset did not have a column containing revenue so one must be created by performing calculations. The total length of stay was calculated by adding the "stays_in_weekend_nights" and "stays_in_week_nights" fields. Next, the total length of stay field was multiplied by the adr field to find the revenue generated per reservation.

After revenue per reservation was calculated, the revenues were summed and grouped by year to discover total annual revenue. 

![image](https://user-images.githubusercontent.com/59523096/222328800-0a56d4d6-a2eb-48f3-84f5-471eea7b43fc.png)
![image](https://user-images.githubusercontent.com/59523096/222329815-a85b8952-0c0b-430c-b647-81ae7e28ce4a.png)

### Develop the SQL

Using the information retrieved from the query I determined that the hotel revenue is increasing by the year as a result of both 2019 and 2020 having higher revenue than 2018. However, there was a decrease in revenue for 2020. This led to another question - why was revenue in 2020 lower than 2019. My first thought was to check the dataset to see if data was present for every month in 2020. This led to the discovery the dataset only contains data up until August 2020.

![image](https://user-images.githubusercontent.com/59523096/222330094-b638bbe0-8ec1-44cb-822b-4499816ac180.png)
![image](https://user-images.githubusercontent.com/59523096/222330147-b5785c84-9e24-4834-8211-53060f14226d.png)

There are two types of hotels contained in the dataset so annual revenue can be further analyzed by hotel type.

![image](https://user-images.githubusercontent.com/59523096/222330566-84c4a2af-a8ae-4ae6-b03d-1f5ec31eee37.png)
![image](https://user-images.githubusercontent.com/59523096/222330597-eb2377eb-e5e0-4579-943b-b7bc271143c4.png)

Both types of hotels saw steady growth in the year 2019.

### Connect Power BI to the database
The data was imported into Power BI for vizualization.

Discounts should be applied to find the annual revenue after discounts. This was done by adding a custom column in Power BI. Calculated by multiplying the length of stay by the discounted daily rate.

Cancellation rate was calculated to help hotel managers understand trends in cancellations and adjust their operations and policies accordingly and revenue was adjusted to not account for reservations that were canceled.

![image](https://user-images.githubusercontent.com/59523096/222331717-991918bd-673a-43fa-84e1-6e2261e60cb3.png)

## Findings

### Cancellations

﻿At 31.56%, July had the highest Cancellation Rate and was 62.04% higher than November, which had the lowest Cancellation Rate at 19.47%.

Across all 12 Month, Cancellation Rate ranged from 19.47% to 31.56%.

### Revenue

﻿Revenue for City Hotel (743.39% increase) and Resort Hotel (346.26% increase) both trended up between Sunday, July 1, 2018 and Monday, September 14, 2020.

﻿The most recent Revenue anomaly was on Monday, August 17, 2020, when Resort Hotel had a high of $36,357.77.

Revenue for Resort Hotel started trending down on Saturday, November 2, 2019, falling by 26.87% ($3,162.25) in 7.57 months.

![image](https://user-images.githubusercontent.com/59523096/222331810-524db77d-3a16-4689-9d64-527a7d9b5df5.png)



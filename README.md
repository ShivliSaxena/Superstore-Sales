# Superstore-Sales
Task 2<br>
Author- Shivli Saxena<br>
Firstly I downloaded the Superstore Sales dataset from Kaggle. I import into the Power BI.<br>
Opened Power Query Editor.<br>
Identified date formatting issues with Order Date and Ship Date. Used Custom Column with:= try Date.FromText([Order Date], "en-GB") to correctly parse dd-mm-yyyy format.<br>
Did the same for Ship Date. Applied changes and loaded the data back to Power BI.<br>
I creared the DAX column by using the formula: Days_Difference = DATEDIFF('Superstore Sales'[Order Date], 'Superstore Sales'[Ship Date], DAY)<br>
This calculates the number of days between each Order Date and Ship Date.<br>
I created a new Date Table using the CALENDAR function to span from the earliest Order Date to 7 days beyond the latest Order Date in the dataset: DateTable = CALENDAR(MIN('Superstore Sales'[Order Date]), MAX('Superstore Sales'[Order Date]) + 7)<br>
I created many-to-one relationship between the DateTable[Date] column and the 'Superstore Sales'[Order Date] column. The relationship was set as single-directional from the Superstore Sales Table to the DateTable to maintain model integrity.<br>
To initiate the dashboard creation, a Matrix visual was added to provide a structured summary of sales across various product categories.This matrix provides a clear tabular summary of sales distribution across categories.<br>
A Table visual was selected from the Visualizations pane and placed onto the report canvas. This table provides granular visibility into order processing times, supporting operational analysis and decision-making.<br>
To enable dynamic filtering and facilitate focused analysis within the dashboard, two Slicer visuals were added one is ship mode , and other is region. These slicers enhance the interactivity of the dashboard, allowing users to drill down and analyze performance metrics specific to selected shipment methods or geographic regions.<br>
To visually represent the average sales distribution across different segments and product categories, a Stacked Bar Chart was added to the dashboard. This visualization provides a clear comparison of average sales across segments and categories, helping stakeholders identify trends and performance variations across customer groups.<br>
To highlight the highest sales performance across different states, a Treemap visual was added to the dashboard. This visual effectively showcases the top-performing states in terms of peak sales figures, offering a quick and intuitive way to identify regional outliers and opportunities.<br>
To analyze the trend of average sales over time, a Line Chart was incorporated into the dashboard. This visualization supports temporal analysis, allowing users to observe patterns, seasonality, and sales fluctuations across the dataset's time span.<br>
The Power BI dashboard provides a comprehensive view of sales performance across categories, segments, and regions. It enables stakeholders to interactively explore the dataset and draw insights. 

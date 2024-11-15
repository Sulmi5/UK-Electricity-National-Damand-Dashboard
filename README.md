# UK Electricity National Damand Dashboard 

### Dashboard Link : https://app.powerbi.com/groups/me/reports/bb691baf-acda-4afc-a6c2-83644cfcfc5a/695936f3f6298a360b70?experience=power-bi

## Problem Statement

The UK's national electricity dashboard reveals challenges in balancing energy demand with sustainable generation sources. In 2023, total national electricity demand decreased by 2.2%, yet seasonal and daily fluctuations persist, especially with high winter demand and summer lows. 
Renewable energy remains underutilized, with non-renewable sources comprising 87.82% of the generation mix. Wind energy utilization averages 27%, peaking in winter, while solar only reaches 10%, with summer highs. This indicates a gap between renewable capacity and effective usage, impacted by seasonal availability and irregular generation.
To meet sustainability goals, the UK must enhance grid flexibility to handle demand spikes and improve renewable utilization. Better demand forecasting, increased renewable infrastructure, and optimized grid operations are essential to transitioning toward a more resilient and sustainable energy system.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor using Transform Data and make sure that all column has the correct data type and has no N/A values. 
- Step 4 : Go through the data and understand using the meta data
- Step 5:  Plan analysis items, and visuals to include to the report and create a layout of the report. 
- Step 6 : Create Date table and aggregate data. 

- Step 7: Create card visuals for Total National Demand / Total Average Demand / Energy Consumption of England and Wales of this year.  Using DAX functions, pull out the difference value and percentage compared to the previous year. 
 
For instance, DAX function is used: 

NDDiffSign = 
    VAR mom = [NDDiff]/[TotalND]
    VAR _sign = IF([NDDiff] >0, "+", "")
    VAR _sign_trend = IF([NDDiff] > 0, "▲", "▼")
    RETURN
    _sign_trend & " " & _sign & FORMAT(mom, "#0.0%" & " | ") & _sign_trend & " " & FORMAT([NDDiff]/1000000, "0.0M")

The conditional formatting is added to the colour of the text. 

- Step 9: Create visuals as follows: 

        1) Line chart:  

        National Electricity Demand by Month  (this year vs previous year) 

        Electricity Demand of Pumping Station 

        Renewable Energy Generation vs Installed Capacity 

        2) Bar Chart

        National Electricity Demand by Day (this year vs previous year)

        3) Pie Chart 

        Distribution of Energy Generation (Renewable vs Non-Renewable Energy) 

        4) Heat Map 

         Renewable Energy Utilization Percentage (Wind Power vs Solar Power) 

- Step 10 : Visual filter (Slicers) was added for the Overview page 

- Step 11: Apply design theme and add a page navigation (Overview , Green Energy 



 # Report Snapshot (Power BI DESKTOP)

![snap1](https://github.com/user-attachments/assets/c0cb6904-8844-4994-a0bf-e026a1f5dfad)

![snap2](https://github.com/user-attachments/assets/c7d1357e-1df3-4eb1-9d2d-57549b8d607a)

# Insights

Two- page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] National Demand Overview
Total National Demand = 456 M MW (-2.2%) 

Total Average Demand = 27.91 K MW (-6.5%) 

Energy Consumption Proportion = 91.6% energy usage occurs in England and Wales 

### [2] Top 3 High Demand Months: January, December, March 
February shows a dip possibly due to a sudden temperature drop in March.

### [3] Top 3 High Demand Days: Tuesday, Wednesday, Thursday 
Consistent weekday demand; weekend demand (Saturday and Sunday) remains lower.

### [4] Pumping Station Demand by Season
High Demand Seasons: December, October, and April.

Seasonal Trends: Lower demand in summer with increases starting mid-April, peaking in September, October, and December

### [5] Energy Generation Distribution
Non-Renewable Energy: 87.82%

Wind Power: 6.82% 

Solar Power: 5.36% 

Renewable Energy comprises less than 20% of total generation, with wind power at 6.82% and solar power at 5.36%.

### [6] Average Renewable Energy Utilization (Generation vs. Installed Capacity) 
Wind Power Utilization: 27% of installed capacity, peaking in winter.

Solar Power Utilization: 10% of installed capacity, peaking in summer.

Given the low solar utilization (around 10%), further solutions are needed to enhance solar efficiency, especially considering the UK's unpredictable weather which limits solar effectiveness.

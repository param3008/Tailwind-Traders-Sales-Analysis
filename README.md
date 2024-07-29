# Microsoft-Power-BI-Certificate-Capstone
### Tailwind Traders Sales Analysis

This project coverage on the topics learned throughout this Professional Certificate, which include the following:--

Clean, transform, and load the data for further analysis.
Cleaning, transforming, and loading data in Power BI
Designing a data model and modeling data in Power BI.
Creating model calculations using DAX and optimizing model performance
Creating and enhancing dashboards and reports for usability, storytelling, and identifying patterns and trends.
Configuring alerts.


### Steps Followed-- 
Raw data downloaed (as they provided) >>> Inserted raw data into power quary editor in Power BI >>> Cleaning and transformation like Removing duplicates, Null values, set proper data types, Clounm Profile, quality and distribution checking >>> Load data into power BI >>> Create Calculated tables(Date Table) and calculated Colunms Using DAX >>> Create data Model >>> create measures using DAX >>> Visualise Data(Report Making) and editing >>> Accessibility setting >>>  Performance optimization >>> Publish in BI Service >>> Creating Dashboard >>> Create App >>> Create Data Alert and Subscription >>> Row level security Setup >>> Data refresh setup.

#### Date table creation Dax Formula
CalendarTable = 
ADDCOLUMNS(
CALENDAR(DATE(2020, 1, 1), DATE(2024, 1, 1)),
"Year", YEAR([Date]),
"Month Number", MONTH([Date]),
"Month", FORMAT([Date], "MMMM"),
"Quarter", QUARTER([Date]),
"Weekday", WEEKDAY([Date]),
"Day", DAY([Date])
)

#### Calvulated table by Exchnage rate formula used 
Sales in USD = ADDCOLUMNS(
    Sales,
    "Country Name", RELATED(Countries[Country Name]),
    "Exchange Rate", RELATED('Exchange Data'[Exchange Rate]),
    "Exchange Currency", RELATED('Exchange Data'[Exchange Currency]),
    "Gross Revenue USD", [Gross Revenue] * RELATED('Exchange Data'[Exchange Rate]),
    "Net Revenue USD", [Net Revenue] * RELATED('Exchange Data'[Exchange Rate]),
    "Total Tax USD", [Total Tax] * RELATED('Exchange Data'[Exchange Rate])
)

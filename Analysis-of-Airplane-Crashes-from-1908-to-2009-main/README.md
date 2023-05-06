# Analysis-of-Airplane-Crashes-from-1908-to-2009
Cleaning, analysis and visualization of Airplane crashes data

----
## Introduction
This project is the second capstone project of the [Data Analysis in Power BI track](https://aka.ms/30DLDATLandingPage) of NG 30 Days of Learning convened by Olanrewaju Oyinbooke ([@TheOyinbooke](https://twitter.com/TheOyinbooke)) for Nigerian students in  a bid to effectively utilise the ongoing ASUU strike.
This documentation includes:
- Project requirements
- Data Sourcing
- Data Cleaning
- Findings
- Reccommendations
- Limitations

----
## Project Requirements
The goal of analysing this data is to get insights that answers some important questions about airplane crashes between 1908 and 2009 which are:
1. What is the total number of crashes within the given period?
2. What is total number of people on board while the plane crashed?
3. What is the total number of fatalities and survivors?
4. Whats is the trend of fatalities and survivors over the period?
5. What are the major causes of airplane crashes?
6. Which year did the most crashes occur?
7. Countries where most crashes occured.
8. Month with the occurrence of most crashes.

----
## Data Sourcing
Data used for analysis was scrapped from [this](https://github.com/theoyinbooke/30Days-of-Learning-Data-Analysis-Using-Power-BI-for-Students) Github repository. The data was originally gotten from [Kaggle](https://www.kaggle.com/datasets/saurograndi/airplane-crashes-since-1908).

----
## Data Cleaning
The data had 13 columns which are: 
- Date
- Time
- Location
- Operator
- Flight #
- Route
- Type
- Registration
- cn/In
- Aboard
- Fatalities
- Ground
- Summary

Some of these columns were removed during the cleaning process because they had more empty rows than non-empty rows and their removal will not have any effect on the analysis. The removed columns are:
- Time
- Flight #
- Route
- cn/In

Empty rows in other columns were appropriately dealt with by replacing those of numerical data type with 0 and those of text data with Unknown.
An index column was added in order to make counting of the total number of crashes easier.
Year and Month columns were also added by extracting them from the date column.
Also, a country column was added by extracting the country name from the location column. Here a problem was encountered: locations in the United States had the name of the states rather than the country name. This was solved by writing some lines of M code to bulk-replace the name of the states with United States of America.
Finally, a Reason column was added by looking for specific words in the Summary column to categorize the reasons into Weather, Shot Down, Fire, Obstacle, Engine Failure, Pilot Error and Explosion.

----
## Findings
Analysis and visualization was done with Microsoft Power BI and the following insights were derived:
- Total number of crashes between 1908 and 2009 is 5,236.
- Total number of passengers aboard is above 140,000 and total number of fatalities is above 105,000. The fatality rate is 72.87%
- Weather is the major cause of plane crash, which accounts for more than 1,600 of the total crashes.
- 1972 is the year with the highest amount of crashes (104). This is also the year with the highest fatalities.
- The top three countries where crashes occur are USA, Brazil and Russia respectively.
- Most crashes occur in December, closely followed by January and August.
- Aeroflot is the operator that has experienced crashes the most, closely followed by the US Air Force.

----
## Reccommendations
1. Weather forecast should be properly done before flights take off.
2. Special attention should be given to countries where most crashes has occured in order to reduce further occurrences.
3. Airline operators should make necessary checks to ensure the plane is in good shape so as to prevent crashes due to engine failure.

----
## Limitations
Although the Summary column provided some information about the reason for some crashes, it is not sufficient for some others.

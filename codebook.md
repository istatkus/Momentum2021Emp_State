
### title: Momemtum Snowflake with Data Robot Employment by State Time Series
#### date: April 1, 2021
### Project Description
Clean and prepare a data set to learn Data Robot  
Clean and prepare a data set to learn Snowflake with Data Robot  

### Subject area 
Select a simple subject area: Employment numbers from The Bureau of Labor Statistcs by State by Year.   
https://www.bls.gov/oes/tables.htm  
Selected the State tables
For initial manual prototype, selecting only major occupations and employment numbers by State
  
### Questions  
What is the predicted employment numbers for future years by State and Occupation. 

### Data selected  
Time Component -- Date -This is not on the file, so I will manually add to the Excel as the release date 5/1/YYYY for each data set
ST -- State code - the 2 caharcter State code
STATE	-- The State Name
OCC_CODE	-- for the manual trial, this will be excluded
OCC_TITLE	-- the occupation group name
GROUP	-- selecting 'Major' 
TOT_EMP -- employee count  
#### The First Step is to analyze and understand the data.

First pass used data from 2012 to 2019 and initially the data did not seem that interesting. 
The Education occupation group appears to have been renamed recently so there is a break - consider combining.   
Some groups are similar and very small  
The cardinality of OCC_TITLE is too large to get usable charts in Power BI - consider combining  


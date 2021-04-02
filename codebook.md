
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

First pass used data from 2012 to 2019 and initially the data did not seem that interesting. Added 2006 to 2011.
The Education occupation group appears to have been renamed recently so there is a break - consider combining. 
Some groups are similar and very small  
Group is not filled in for all the sets other than Major. 
The cardinality of OCC_TITLE is too large to get usable charts in Power BI - consider combining.  
The occupation names may change or have different case or spelling. 
The latest sets have extra columns.  
Employment Totals missing on some. Imputed as average or next. 
Interpretation of data needs understanding of Department of Labor Statistics hierarchies. Example: Education Administration is under Management, Healtcare aids and assistants separate from Nurses, Doctors, technitians.  


<img src="https://user-images.githubusercontent.com/12059492/113344759-81630c80-92ff-11eb-8c58-2f0aafc613ec.png" width="950" height="470"> 
  
PowerBi samples data theer are 54 States, includes Guam, PuertoRico  
  
![image](https://user-images.githubusercontent.com/12059492/113347955-f1739180-9303-11eb-82a9-8786feda4c1e.png)

![image](https://user-images.githubusercontent.com/12059492/113351735-436ae600-9309-11eb-975e-e82b38d279d6.png)  
![image](https://user-images.githubusercontent.com/12059492/113352425-3c90a300-930a-11eb-9300-4b454fbe58d2.png)  
![image](https://user-images.githubusercontent.com/12059492/113415749-e107f900-938d-11eb-9768-b6aae8af839a.png)



### Data Robot
Based on initial data exploration in PowerBi and SAS, I cleansed the names and changed to upper case.
Missing Employment numbers were imputed as next, or average
![image](https://user-images.githubusercontent.com/12059492/113415810-fd0b9a80-938d-11eb-82ba-545bf3f4c517.png)    
tot_emp will be set as the target  
Set up time aware modeling  
 
<img src="https://user-images.githubusercontent.com/12059492/113416010-5f649b00-938e-11eb-999c-de95ee550150.png" width="250" height="150"> 

![image](https://user-images.githubusercontent.com/12059492/113416044-74d9c500-938e-11eb-85a5-3ed704a7d3f4.png)  










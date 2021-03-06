
## title: Momemtum Snowflake with Data Robot Employment by State Time Series
#### date: April 1, 2021
## Project Description
Clean and prepare a data set to learn Data Robot  
Clean and prepare a data set to learn Snowflake with Data Robot  

## Subject area 
Select a simple subject area: Employment numbers from The Bureau of Labor Statistcs by State by Year.   
https://www.bls.gov/oes/tables.htm  
Selected the State tables
For initial manual prototype, selecting only major occupations and employment numbers by State
  
## Questions  
What is the predicted employment numbers for future years by State and Occupation. 

### Data selected  
Time Component -- Date -This is not on the file, so I will manually add to the Excel as the release date 5/1/YYYY for each data set  
ST -- State code - the 2 character State code  
STATE	-- The State Name  
OCC_CODE	-- for the manual trial, this will be excluded  
OCC_TITLE	-- the occupation group name  
GROUP	-- selecting 'Major'  
TOT_EMP -- employee count  

## The First Step is to analyze and understand the data.

First pass used data from 2012 to 2019 and initially the data did not seem that interesting. Added 2006 to 2011.
The Education occupation group appears to have been renamed recently so there is a break - consider combining. 
Some groups are similar and very small  
Group is not filled in for all the sets other than Major. 
The cardinality of OCC_TITLE is too large to get usable charts in Power BI - consider combining.  
The occupation names may change or have different case or spelling. 
The latest sets have extra columns.  
Employment Totals missing on some. Imputed as average or next. 
Interpretation of data needs understanding of Department of Labor Statistics hierarchies. Example: Education Administration is under Management, Healtcare aids and assistants separate from Nurses, Doctors, technicians.  

## PowerBI
<img src="https://user-images.githubusercontent.com/12059492/113344759-81630c80-92ff-11eb-8c58-2f0aafc613ec.png" width="950" height="470"> 

##### There are 54 States, includes Guam, PuertoRico  , Power BI used a data sample
  
<img src="https://user-images.githubusercontent.com/12059492/113347955-f1739180-9303-11eb-82a9-8786feda4c1e.png" width="950" height="470"> 

##### All State and Computer  

<img src="https://user-images.githubusercontent.com/12059492/113436976-c5afe480-93b3-11eb-97e5-b08a016712f7.png" width="950" height="470">   

## SAS Data Exploration  
<img src="https://user-images.githubusercontent.com/12059492/113351735-436ae600-9309-11eb-975e-e82b38d279d6.png" width="950" height="310">  

<img src="https://user-images.githubusercontent.com/12059492/113352425-3c90a300-930a-11eb-9300-4b454fbe58d2.png" width="314" height="456">  
##### SAS had difficulty with 3 State abbreviations 
<img src="https://user-images.githubusercontent.com/12059492/113420525-7c519c00-9397-11eb-9e78-97565586c75a.png" width="436" height="193">   
<img src="https://user-images.githubusercontent.com/12059492/113437099-0576cc00-93b4-11eb-81ac-13f4d991885c.png" width="840" height="638">  
  
<img src="https://user-images.githubusercontent.com/12059492/113420272-077e6200-9397-11eb-91f0-3e24093ae6e4.png" width="950" height="546">  
 
##### Simple Forecasting  
<img src="https://user-images.githubusercontent.com/12059492/113422285-65607900-939a-11eb-9554-b9d3ae56b211.png" width="950" height="550">
<img src="https://user-images.githubusercontent.com/12059492/113424701-95aa1680-939e-11eb-83e8-4a66d3a45584.png" width="950" height="660">   
  
##### SAS Built in Models  
<img src="https://user-images.githubusercontent.com/12059492/113436551-e88dc900-93b2-11eb-91d6-be9e497cb47f.png" width="431" height="100">   


## Forecasting PowerBI  
Combined State Population and State Employment to produce connected report that contains a line chart with forecast  
![image](https://user-images.githubusercontent.com/12059492/114080554-86810800-9879-11eb-89fa-e1e079d40e4e.png)  
![image](https://user-images.githubusercontent.com/12059492/114080840-d65fcf00-9879-11eb-857b-6180635e35af.png)  

![image](https://user-images.githubusercontent.com/12059492/114079207-e4145500-9877-11eb-89bb-78d4e073d22e.png)



## Data Robot
Based on initial data exploration in PowerBi and SAS, I cleansed the names and changed to upper case.
Missing Employment numbers were imputed as next, or average
![image](https://user-images.githubusercontent.com/12059492/113415810-fd0b9a80-938d-11eb-82ba-545bf3f4c517.png)    
tot_emp will be set as the target  
##### Set up time aware modeling  
 
<img src="https://user-images.githubusercontent.com/12059492/113416010-5f649b00-938e-11eb-999c-de95ee550150.png" width="250" height="150"> 
##### Only Automated with backtesting is available the other option is disabled  

![image](https://user-images.githubusercontent.com/12059492/113416044-74d9c500-938e-11eb-85a5-3ed704a7d3f4.png)  

![image](https://user-images.githubusercontent.com/12059492/113418041-b10f2480-9392-11eb-9493-7444018afd90.png)  

##### None of the Advanced options are applicable  

![image](https://user-images.githubusercontent.com/12059492/113418167-f2073900-9392-11eb-9df5-6dfb0f6638a1.png)  

##### You can select an alternate method for model optimization    

![image](https://user-images.githubusercontent.com/12059492/113418234-1400bb80-9393-11eb-826e-519328856ad9.png)  

##### We are expecting a prediction by State, Occupation. These exist for each Year  

![image](https://user-images.githubusercontent.com/12059492/113418404-6b9f2700-9393-11eb-8b8b-d25f3343dcaf.png)  

##### Created a custom feature list  
![image](https://user-images.githubusercontent.com/12059492/113418702-fb44d580-9393-11eb-85a1-5789ebcee084.png) 

##### None of the features are applicable for the transform feature option. I did not explore this for this data set. It looks to be a minimal transform capability. 

![image](https://user-images.githubusercontent.com/12059492/113418854-4ced6000-9394-11eb-8599-3b7ee106a018.png)  
![image](https://user-images.githubusercontent.com/12059492/113418926-6db5b580-9394-11eb-9700-656048dbb3a0.png)  

##### Selected Model  

![image](https://user-images.githubusercontent.com/12059492/113420659-b4f17580-9397-11eb-8db9-ba1f437e5c62.png)  
![image](https://user-images.githubusercontent.com/12059492/113426324-4b766480-93a1-11eb-9771-e291e529d664.png)  
![image](https://user-images.githubusercontent.com/12059492/113427041-5978b500-93a2-11eb-8fe0-1035114257c8.png)  
![image](https://user-images.githubusercontent.com/12059492/113427205-a2306e00-93a2-11eb-82af-c798142d70b8.png)  

##### Download prediction  

![image](https://user-images.githubusercontent.com/12059492/113427555-3c90b180-93a3-11eb-8c39-2ab1b90685ea.png)  

##### I need to rename the downloaded file, else I get an error trying to open with Excel  
![image](https://user-images.githubusercontent.com/12059492/113427674-7b266c00-93a3-11eb-9ec0-b0f2e0359fe8.png)  

##### You can add or change associated items withour re-predicting. I changed to use State name to compare to last model.  
![image](https://user-images.githubusercontent.com/12059492/113428185-57aff100-93a4-11eb-87f6-e56313e694c3.png) 

##### Creating a deployment  

![image](https://user-images.githubusercontent.com/12059492/113427465-0fdc9a00-93a3-11eb-8427-51708bb7afa3.png)  

##### Download Exportable Charts  
![image](https://user-images.githubusercontent.com/12059492/113430260-d9554e00-93a7-11eb-8a1c-dbb7fd383b3d.png)

## Some Results  
##### First model - fewer years had stronger downward trend due to 2020
![image](https://user-images.githubusercontent.com/12059492/113438045-c9446b00-93b5-11eb-8e93-ebdd7df8b039.png)  
##### Excel Slope and Intercept Florida and Computer  
![image](https://user-images.githubusercontent.com/12059492/113438170-07da2580-93b6-11eb-9c0c-de9b6e846379.png)  
##### SAS Linear Regression 95% Confidence Interval  
![image](https://user-images.githubusercontent.com/12059492/113438245-2f30f280-93b6-11eb-90d0-d312f632b264.png) 

### Using Paxata to clean the data sets and join them  

![image](https://user-images.githubusercontent.com/12059492/113872262-bc42c580-9781-11eb-9ba8-2ae049463162.png)  
Adding a join column for just year.  
![image](https://user-images.githubusercontent.com/12059492/113905829-94635a00-97a1-11eb-8144-8c553cc88c38.png)
  
Re-running Time series with population
![image](https://user-images.githubusercontent.com/12059492/113874452-cd8cd180-9783-11eb-9c06-e9d6b9f23a84.png)  

After cleansing and combining with Paxata and re-running through Data Robot, the Feature Impact results would imply that the population and population over 18 growth had little impact on the model itself.  
![image](https://user-images.githubusercontent.com/12059492/113904948-9c6eca00-97a0-11eb-9980-5f662f25af1c.png)  








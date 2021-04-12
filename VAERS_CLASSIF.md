## title: Momemtum Vaccine reaction classification  
#### date: April 81, 2021  
## Project Description  
Clean and prepare a data set to learn Data Robot, Praxata  
NOTE: The data is TEST quality, no causation or correlation can be derived for real. Data is not just recent vaccines, some data historical.  
## Subject area 
Select a simple subject area: VAERS vaccine reaction with died column  

### Sources
VAERS  AS USED IN THIS EXERCISE: Data challenges: small data set, doesnt include follow up, manual text fields with no standardization, for testing a classification model only. 
https://vaers.hhs.gov/eSubDownload/index.jsp?fn=2021VAERSData.zip  

### Steps Explore the data  
Chose to explore in SAS, see above comment on data challenges. Initial load AS IS to DATA ROBOT 
yielded poor modeling potential. Second attempt based on performing some data transformations to see if modeling potential improves. 

### Uploaded to PAXATA 2 files  
First was ID and symptoms as columns. Data presents as 5 per row, Id can have multiple rows, not all columns contain data. 
De-pivoted to rows.  
Removed null rows.  
![image](https://user-images.githubusercontent.com/12059492/114238674-04fda880-9953-11eb-8106-301380da11f6.png)
Second file contained ID, additional details and flags.  
Converted some Y/missing to binary, converted some text to binary, removed numerous columns, joined to first table for symptom count.  
![image](https://user-images.githubusercontent.com/12059492/114239013-7f2e2d00-9953-11eb-98cd-6232b5829df4.png)  
![image](https://user-images.githubusercontent.com/12059492/114239075-92d99380-9953-11eb-8616-99a0584fd458.png)  

#### Replace - convert Y/blank to 0/1

#### Text clustering  
![image](https://user-images.githubusercontent.com/12059492/114425434-1202dd80-9b87-11eb-951e-18bf9c0fdaa6.png)

#### Saved and exported manually.  

![image](https://user-images.githubusercontent.com/12059492/114238064-011d5680-9952-11eb-97d1-ae1f134ab925.png)  


### Upload to DATA ROBOT
![image](https://user-images.githubusercontent.com/12059492/114238021-eea31d00-9951-11eb-9861-9db1f6c6512b.png)  
### Review, select target and run Quick, view feature importance  
![image](https://user-images.githubusercontent.com/12059492/114239653-55c1d100-9954-11eb-9bdb-b908ad9bedfe.png)  




# HR-Dashboard-
## Creating HR Dashboard using Power BI

In this project, varies measures are calculated using powerBI.

Steps are:

-Load the data to Power BI from Excel

-To arrange the data using Power Query 

-Calculation data using the DAX formula

-Adding Conditional column

-Merge different table in PowerBI

-Using the Navigator

### CALCULATIONS

*-Total Employee* 
```
Total Employees = COUNTROWS('HR Analytics Data')
```
*-Male and Female Employees and percentage of total*
```
Male = CALCULATE([Total Employees],'HR Analytics Data'[Gender]="male")

% male = DIVIDE([Male],[Total Employees],0)

Female = CALCULATE([Total Employees],'HR Analytics Data'[Gender]="female")

% female = DIVIDE([Female],[Total Employees],0)
```
*-Due For Promotion and not due and percantage of total*
```
Due for promotion = CALCULATE([Total Employees], 'HR Analytics Data'[Promotion Status]="due for promotion")

% Due for promotion = DIVIDE([Due for promotion], [Total Employees],0)

Not due = CALCULATE([Total Employees], 'HR Analytics Data'[Promotion Status]="not due")

% Not Due = DIVIDE([Not due], [Total Employees],0)
```
*-Calculating people count on service and retreachment and percantage of total*
```
On Service = IF(ISBLANK( CALCULATE([Total Employees], 'HR Analytics Data'[Retreanchment status]="on services")),0,CALCULATE([Total Employees], 'HR Analytics Data'[Retreanchment status]="on services"))

% Service = DIVIDE([On Service], [Total Employees],0)

retreachment = IF(ISBLANK( CALCULATE([Total Employees], 'HR Analytics Data'[Retreanchment status]="retreachment")),0,CALCULATE([Total Employees], 'HR Analytics Data'[Retreanchment status]="retreachment"))

% Retreanche = DIVIDE([retreachment], [Total Employees],0)
```
*-Calculate the performance for each employee and classification and  percantage of total*
```
High Rating count = CALCULATE([Total Employees], 'HR Analytics Data'[Performans Rating]="High Rating")

% High rating = DIVIDE([High Rating count], [Total Employees],0)

Low Rating count = CALCULATE([Total Employees], 'HR Analytics Data'[Performans Rating]="Low Rating")

% Low rating = DIVIDE([Low Rating count], [Total Employees],0)
```

![image](https://github.com/ipekhisar/HR-Dashboard-/assets/150418764/661666c5-6892-48ed-9b02-af54b8ae877d)



# PWC Power BI Virtual internship Task 3 - HR Diversity and Inclusion 

## Problem Statement :

The purpose of this analysis is to:

- Define proper KPIs in hiring, promotion, performance and turnover
- Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.
- The following measures could help to define proper KPIs:

- '#' of men
- '#' of women
- '#' of leavers
- % employees promoted (FY21)
- % of women promoted
- % of hires men
- % turnover
- Average performance rating: men
- Average performance rating: women

## Datasource:

Dataset: [03 Diversity-Inclusion-Dataset.xlsx](https://github.com/sonali-guptaa/hr_diversity_-_inclusion_analysis/files/14510418/03.Diversity-Inclusion-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset is then loaded into Microsoft Power BI Desktop for visualization.

## Dataset Description:

Diversity and Inclusion dataset contains `32 columns and 500 rows` of observation. Dataset includes columns like:

Employee ID: Represents the unique number of the employee in the dataset
Gender: Describes the gender of the employee
Job Level after FY20 promotions: Describes the job level of the employee after being promoted in FY20
New hire FY20?: Describes if the employee is a new hire in FY20
FY20 Performance Rating: Represents the performance rating of the employee in FY20
Promotion in FY21?: Describes if the employee is being promoted in FY21
In base group for Promotion FY21: Describes if the employee is being selected for promoted in FY21
Target hire balance	Describes the target hire balance of the employee
FY20 leaver?: Describes if the employee is a leaver in FY20
In base group for turnover FY20: Describes if the employee is in a group for turnover in FY20
Department @01.07.2020: Describes the department each employee belongs to as at January 7, 2020
Leaver FY: Describes if the employee is a leaver in a FY
Job Level after FY21 promotions: Describes the job level of the employee after being promoted in FY21
Last Department in FY20: Describes the last department each employee belongs in FY20
FTE group: Describes if the employee belongs to a FTE group
Time type: Describes the contract type employee
Department & JL group PRA status: Describes the department and JL group PRA status of the employee
Department & JL group for PRA: Describes the department and JL group PRA of the employee
Job Level group PRA status: Describes the job level group PRA status of the employee
Job Level group for PRA: Describes the job level group PRA of the employee
Time in Job Level @01.07.2020: Describes the time in job level of the employee
Job Level before FY20 promotions: Describes the job level employee before being promoted in FY20
Promotion in FY20?: Describes if the employee is being promoted in FY20
FY19 Performance Rating: Describes the performance rating of the employee in FY19
Age group: Describes the age group of the employee
Age @01.07.2020: Represents the age of the employee as at January 07, 2020
Nationality 1: Describes the nationality of the employee in state level
Region group: nationality 1	Describes the nationality of the employee in country level
Broad region group: nationality 1	Describes the nationality of the employee in regional level
Last hire date: Describes the last hire date of the employee
Years since last hire: Represents the number of years since last hire of the employee
Rand: generates random number for each entry in the dataset

## Data Cleaning

- Each of the columns in the table were validated to have the correct data type too.

## Calculated Measures created using DAX:

Measures used in  all visualization are:

- # Avg Men Rating = `CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Male"))`

- # female = `CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Female"))`

- # male = `CALCULATE(DISTINCTCOUNT('Pharma Group AG'[Employee ID]), FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Male"))`

- # Promoted FY20 = `CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Promotion in FY20?]="Y")+CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Promotion in FY21?]="Yes")`

- #Avg Female Rating = `CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG', 'Pharma Group AG'[Gender] = "Female"))`

- #Employee Turnover = `DIVIDE('Pharma Group AG'[#Leaver],COUNT('Pharma Group AG'[Employee ID]),0)`

- #Leaver = `CALCULATE(COUNT('Pharma Group AG'[FY20 leaver?]), 'Pharma Group AG'[FY20 leaver?]="Yes")`

- % female = `DIVIDE('Pharma Group AG'[# female], 'Pharma Group AG'[# female] + 'Pharma Group AG'[# male])`

- % male = `DIVIDE('Pharma Group AG'[# male], 'Pharma Group AG'[# female] + 'Pharma Group AG'[# male])`


## Data Visualization (Dashboard):

Dashboard created using the calculated measures in Microsoft Power BI Desktop:

![1](https://github.com/sonali-guptaa/hr_diversity_-_inclusion_analysis/assets/151986702/8b57dfe3-3abd-4e3f-bc12-016116dad298)

![2](https://github.com/sonali-guptaa/hr_diversity_-_inclusion_analysis/assets/151986702/4947d885-a9e3-4489-82c0-e0b728f001e1)

## Insights:

As per the visualizations, it has been deduced that :

- In total, 205 females and 295 males are there in the company.
- 41% of hires were female
- 59% of hires were male
- 2.41 is the average rating of men
- 2.42 is the average rating of women
- In age group 30–39, the total number of employees within this range totals 115 while the females total 59.
- Also, it seems that more male employees in are promoted to higher-level job profiles than females.
- The higher turnover percentage is among female employees.

## Recommendation:

Some recommendations based on the analysis are:

- There is a need to look into the rate of employment of staffs from different nationality, people of different nationality should be encouraged to take up roles in the company.

- From the analysis above the rate of Diversity and Inclusion is low considering how that there's gender imbalance in how staffs are hired and promoted.

---

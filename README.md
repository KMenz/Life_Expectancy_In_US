# Analyzing Life Expectancy In The US
## By Kevin Menz, Angela Spirou, Lauren Gama, Myke London, and Connor Healy
The goal of this project was to locate data relating to Life Expectancy across the United States over time and to analyze it using Data Science tools in order to come up with conclusions how life expectancy differs across different variables.

## The Datasets
https://healthinequality.org/data/ - The Health Inequality Project  - Set of multiple datasets
https://data.hrsa.gov/data/download - Health Resources & Services Administration  
https://hifld-geoplatform.opendata.arcgis.com/ - Homeland Infrastructure Foundation-Level Data

## The Tools
The project was done almost entirely in Python and Jupyter Notebook using a various set of libraries including:
* Pandas
* MatPlotLib
* Seaborn
* NumPy
* SciPy

## The Process
We decided to split up who would answer questions regarding different variables that could potentially affect life expectancy. These questions were :
* Are there differences in the national LE by gender?
* Are there differences in national LE by income?
* Which states have the highest/lowest LE?
* Is LE affected by the percent of a state's uninsured population, percent of African American population, and percent of Hispanic population
* Are there differences in state LE by access to quality health care?

Each person then took on each question by cleaning the data, analyzing the data, and reporting their findings


# Analysis and Answers
## Q1 - Gender
Used the Health Inequality Project dataset. Pulled into Jupyter for cleaning first. The columns were cut down to only just the neccessary ones for analysis. 

The analysis involved creating individual dataframes for males and females, then show the national average Life Expectancy per year per gender. We then created a line graph to visualize the average differences.

![Project 1 Line Graph](https://user-images.githubusercontent.com/40543168/56840074-943b4f80-6853-11e9-9cab-88fa7ca4b85c.png)

We found that the Female Average LE s 85.54 years while the Male Average LE is 81.81 years. 

## Q2 - Differences by Income
Used the Health Inequality Project dataset. Was cleaned by cutting down columns, and adding quartiles for income percentiles for easier analysis. 

![Project 1 Gender Cleaning](https://user-images.githubusercontent.com/40543168/56839889-b97b8e00-6852-11e9-8182-256a9d6580c9.PNG)

We then visualized the quartiles using a line chart and a box plot.

![Project 1 Income Line 1](https://user-images.githubusercontent.com/40543168/56840841-d9fa1700-6857-11e9-99ee-9de265362380.png)

![Project 1 Income Box](https://user-images.githubusercontent.com/40543168/56840849-e41c1580-6857-11e9-871c-7fbf2f7d2168.png)

We also wanted to compare how Females and Males differed for individual quarters. So we looked at Q1 and Q4 to see the difference.

![Project 1 Female LE Income](https://user-images.githubusercontent.com/40543168/56841007-f9de0a80-6858-11e9-86d5-b8f725a1480b.png)

![PRoject 1 Male LE Income](https://user-images.githubusercontent.com/40543168/56841016-02364580-6859-11e9-8e30-32cf7a86302b.png)

## Q3 - States with High/Low LE
Used the Health Inequality Project dataset. Was cleaned by cutting down columns, and then deciding to use the average of 4 quarters worth of LE as the measure of LE for each State.

Plotted the top 5 and bottom 5 states for Male and Female and showed the opposite gender as a comparison.

![Project 1 State High Male](https://user-images.githubusercontent.com/40543168/56841129-d2d40880-6859-11e9-8a8d-94e054fc053a.png)
![Project 1 State High Female](https://user-images.githubusercontent.com/40543168/56841143-df586100-6859-11e9-842b-dd500311ca36.png)

This showed that the state with the highest male LE is Montana at 83.08 years and the state with the highest female LE is Vermont at 86.18 years. This is consistent with our analysis earlier that females tend to live longer in general. 

![Project 1 State Low Male](https://user-images.githubusercontent.com/40543168/56841197-4249f800-685a-11e9-9765-4178c93ecf37.png)
![Project 1 State Low Female](https://user-images.githubusercontent.com/40543168/56841202-49710600-685a-11e9-9d78-aeda6812085a.png)

This showed us that the state with the lowest male and female LE is Nevada at 79.64 and 86.18 years respectively. Some other takeaways from this analysis were that there is an average difference of 3.3 years per state between genders. Also, top and bottom states differ between genders, if only slightly. There were a few common states as well.

## Q4 - LE vs Uninsured, African American population, Hispanic population
Used the Health Inequality Project dataset. Was cleaned by cutting down columns, then found the weight average for the county population against each column of interest. With the state averages for the data of interest calculated, we then merged this dataframe with the state dataframe from Q3 to include the Life Expectancy’s by state.

![Project 1 State Uninsured](https://user-images.githubusercontent.com/40543168/56841398-7eca2380-685b-11e9-8af1-c5c66be54c11.png)

By charting the percent uninsured by state, and comparing against Q3's LE bar chart, we can see there are several states, including Vermont and Montana, which rank among the states with the most amount of insured residents and the greatest LE. Conversely, states, such as Nevada, have the lowest LE and have a population which ranks among the most uninsured.  

![Project 1 Scatter](https://user-images.githubusercontent.com/40543168/56841444-c781dc80-685b-11e9-83b4-b817dcee8fb9.png)

We created a scatter plot to see if there is a direct correlation between State Average LE and Percent Uninsured by State. Because the chart did not appear to show a clear relationship between the variables, we ran a pearson correlation. The pearson correlation revealed that the LE will decrease the higher the percent of a state’s uninsured population increases.

We then created scatter plots to see the relationship between State Average LE and Percent of a State’s African-American and Hispanic population.

![Project 1 Scatter AA](https://user-images.githubusercontent.com/40543168/56841483-03b53d00-685c-11e9-950b-26c2d7756ac8.png)
![Project 1 Scatter His](https://user-images.githubusercontent.com/40543168/56841485-10d22c00-685c-11e9-8bf4-838d49b2a691.png)

As well, the chart did not seem to show a clear relationship, so we ran a pearson correlation for both. In doing so, the pearson correlation showed that the LE will decrease the higher the percent of a state’s African-American and Hispanic population increases.

## Q5 - State LE vs. Quality Health Care
Used the HIFLD Data for County and State Hospital data and the HRSA for Health Care Qualtity. 

First looked at Hospitals vs. Medically Underserved Areas. Used the IMU score as a standard for quality. It's a scale from 0 – 100 to determine the value of performance on demographic and health care facilities in a given county.

![Project 1 Map Blue](https://user-images.githubusercontent.com/40543168/56841674-285de480-685d-11e9-8a92-6d9cd11723dc.png)
![Project 1 Map Orange](https://user-images.githubusercontent.com/40543168/56841686-30b61f80-685d-11e9-9197-cb76618e58e3.png)

You can see in the blue the number of hospitals, and in the orange the IMU score. We then chose two states as our sampels, Alabama and Minnesota. These have an average LE of about 77 ad 82 respectively, while Alabama has 133 Health Care Facilities and Minnesota has 104.

![Project 1 Alabama Map](https://user-images.githubusercontent.com/40543168/56841780-d5386180-685d-11e9-9e8f-cf6c8c2fd208.png)
![Project 1 Minn Map](https://user-images.githubusercontent.com/40543168/56841782-dcf80600-685d-11e9-8614-de27ca5667fe.png)

Despite having more Health Care facilities, you can see that 18% of Alabama's population lives within IMU >60% while only 3% of Minnesota's population lives within IMU > 60%. This could explain why Alabama's LE is lower. 

![Project 1 Alabama IMU](https://user-images.githubusercontent.com/40543168/56841846-27798280-685e-11e9-80f0-d4a75131af30.png)
![Project 1 Minn IMU](https://user-images.githubusercontent.com/40543168/56841850-306a5400-685e-11e9-86a3-6e0bea81e1b6.png)




 



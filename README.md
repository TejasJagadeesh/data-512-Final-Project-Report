# Final Project Report
# Analysis of OASDI and SSI payments across all states in US

Tejas Jagadeesh  
DATA 512 (Human-Centered Data Science)  
University of Washington, Fall 2018  
  
# Introduction 
 
OASDI stands for Old-Age, Survivors, Disability Insurance. It is part of Social Security Disability program. It is provided as support to people who are retired and families (dependent spouses and children) of workers have died. Additional details on its history can be found here on Wikipedia - https://en.wikipedia.org/wiki/Social_Security_(United_States)  
  
SSI stands for Supplemental Security Income. It is part of Social Security and involves monthly payment as support to people with limited income and people who are disabled, blind or aged 65 years and above. Additional details about SSI can be found here - https://www.ssa.gov/ssi/text-over-ussi.htm   
  
Both programs are administered by Social Security Administration (SSA) - https://www.ssa.gov/.
The key difference between these two programs, as mentioned in the link (https://www.ssa.gov/ssi/text-over-ussi.htm) is:
“Social Security benefits may be paid to you and certain members of your family if you are “insured” meaning you worked long enough and paid Social Security taxes. Unlike Social Security benefits, SSI benefits are not based on your prior work or a family member's prior work.”  
  
Each year congressional reports are published with information of SSI and OSDI payments made by each state. This report includes information about no. of recipients in each category and the total payments made for each state.  
  
I have analyzed this data for the years 2013, 2014, 2015, 2016 and 2017. I performed this analysis as part of my final project for Human-Centered Data Science course (DATA 512) during Fall 2018 at the University of Washington. Keeping in mind the human centered aspect of this course, my intent was to get a sense of distribution of people benefiting from OASDI and SSI across US. 
 
OASDI and SSI are very important support systems US has for those who are in need of financial assistance for survival and critical health needs. So it is important to analyze the spending to ensure there is equitable distribution and there are no anomalies. It is also important to analyze and identify if there are any strange trends which may give rise some to more research questions.
  
# Data

The data consists of congressional statistics reports (OASDI and SSI fact sheets) published for each year that includes the following information for each state. Each report has two types of information for each state:  
  
- OASDI Payments
- SSI Payments
  
### OASDI Payments:
The data for OASDI is organized in tabular format with the following data presented for each congressional district within each state. There is also a summation provided at each state level.  
The information provided is:  
  
| Column | Datatype | Description |
|-----|------------|----|
|Total workers|Number|Total Number of beneficiaries|
|Retired workers| Number |Number of beneficiaries who are Retired workers|
|Disabled workers| Number |Number of beneficiaries who are Disabled workers|
|Widow(er)s and parents| Number |Number of beneficiaries who are Widow(er)s and parents|
|Spouses| Number |Number of beneficiaries who are Spouses of a worker who is retired or disabled|
|Children| Number |Number of beneficiaries who are Children of a worker who is retired, deceased, or disabled|
|All beneficiaries| Number |Total monthly benefits (thousands of dollars) for All beneficiaries|
|Retired workers payments| Number |Total monthly benefits (thousands of dollars) for Retired Workers|
|Widow(er)s and parents payments| Number |Total monthly benefits (thousands of dollars) for Widow(er)s and parents|
|Number of beneficiaries aged 65 or older| Number | Total Number of beneficiaries aged 65 or older|
  
### SSI Payments:
The data for SSI is organized in tabular format with the following data presented for each congressional district within each state. There is also a summation provided at each state level.  
The information provided is:  
  
| Column | Datatype | Description |
|-----|------------|----|
|Total recipients|Number|Total Number of recipients|
|Aged| Number |Number of recipients who are Aged 65 years of older|
|Blind| Number | Number of recipients who are Blind|
|Disabled| Number | Number of recipients who are Disabled|
|Total monthly payments| Number |Total monthly payments (thousands of dollars)|
|Aged Payments| Number | Total monthly payments (thousands of dollars) for recipients who are Aged 65 years or older|
|Blind Payments| Number | Total monthly payments (thousands of dollars) for recipients who are Blind|
|Disabled Payments| Number | Total monthly payments (thousands of dollars) for recipients who are Disabled|
|Total recipients with OASDI|Number|Total Number of recipients who are receiving both SSI payments and Social Security benefits|
|Number of OASDI beneficiaries aged 65 or older | Number | Total Number of beneficiaries aged 65 or older who are receiving both SSI payments and Social Security benefits |
  
US population data in numbers for the years 2013, 2014, 2015, 2016 and 2017.  
US geographical map shapefile.

### Sources:
The above data can be found in the following links:  
  
| Year | Link |
|-----|------------|
|2013|https://catalog.data.gov/dataset/congressional-statistics-a0610|
|2014|https://catalog.data.gov/dataset/congressional-statistics-december-2014|
|2015|https://www.ssa.gov/policy/docs/factsheets/cong_stats/2015/index.html|
|2016|https://www.ssa.gov/policy/docs/factsheets/cong_stats/2016/index.html|
|2017|https://catalog.data.gov/dataset/congressional-statistics-december-2017|
  
Popultaion Data has been sourced from https://data.worldbank.org/indicator/SP.POP.TOTL?locations=US  
US States shapefile has been sourced from https://github.com/python-visualization/folium/blob/master/examples/data/us-states.json

### Licenses:
The data for years 2013, 2014 and 2017 are released under Creative Commons CCZero license (http://opendefinition.org/licenses/cc-zero/) as can be found in the links above. The sources for years 2015 and 2016 are not specifically provided in the source https://catalog.data.gov. However, the data for years 2015 and 2015 was available in the same root source as for years 2013, 2014 and 2017. Considering that the data for the years 2013, 2014 and 2017 were released under CCZero license, I assumed that the data for 2015 and 2016 is also covered under the same license since the nature of data is exactly the same.

Popultaion data has been released under CC BY-4.0 license (https://datacatalog.worldbank.org/public-licenses#cc-by)  
US States shapefile has been released under MIT License - https://github.com/python-visualization/folium/blob/master/LICENSE.txt  
  
# Research Items
  
I didn’t have any specific hypothesis to test. However, I wanted to analyze the data to see: 

1. Distribution of beneficiaries of OASDI and SSI across US.
2. Distribution of spending of OASDI and SSI across US.
3. Trends in distribution of beneficiaries of OASDI and SSI across US.
4. Trends in the OASDI and SSI spending.
5. Average increase in spending per person for OASDI.
6. Average increase in spending per person for SSI.
7. Comparison of OASDI and SSI spending.
8. Who are the primary beneficiaries of OASDI and SSI?
9. Comparison of increase in spending % of OASDI and SSI (for largest category) against change in % increase of US population.  
  
# Research Findings  
  
The analysis of first 4 Research Items didn't reveal any major trends to indicate any sign of bias in the equitable distribution of OASDI and SSI payments and beneficiaries. The distributions appear to be aligned well with the population densities.

However the rest of the items had the following observations and associated research questions:

Item #5 - Average increase in spending per person for OASDI  
- The average increase in spending per person doesn't appear to align with the top spenders of OASDI as seen above.
- The top spenders don't feature in the list of top 10 states with highest average increase in spending per person for OASDI.
- This indicates that the states with lesser population densities appear to have the highest increase in average spending per person for OASDI. Further anlaysis with the help of additional data is required to understand why this is the case.
- The interesting part is that the average increase per person over the last few years has only been between 23 USD and 33 USD which doesn't appear to be high enough to make any significant impact in the lives of the beneficiaries.
 
Item #6 - Average increase in spending per person for SSI 
- The average increase in spending per person doesn't appear to align with the top spenders of SSI as seen above. It also appears to be even across all states.
- The top spenders don't feature in the list of top 10 states with highest average increase in spending per person for SSI.
- This indicates that the states with lesser population densities appear to have the highest increase in average spending per person for SSI. Further anlaysis with the help of additional data is required to understand why this is the case.
- New York is the only state which has had a decrease in average spending per person for SSI.
- The interesting part is that the average increase per person over the last few years has only been between 0 USD and 15 USD which doesn't appear to be high enough to make any significant impact in the lives of the beneficiaries.
 
Item #7 - Comparison of OASDI and SSI spending 
- SSI appears to be only a small fraction of OASDI spending.
- It could be because OASDI is funded through employment and so has a bigger budget.
- The budget difference clearly indicates how the benefits are skewed towards those who can work and effectively contribute towards the economy and society in general. Though SSI appears to cover all those individuals who are incapable of working and contribute towards the social security tax, the relative size of the budget indicates that there could be some bias here which needs to be further investigated with additional data.
 
Item #8 - Who are the primary beneficiaries of OASDI and SSI? 
- For OASDI, the retired workers appear to get the lion's share.
- For OASDI, the retired workers also appear to be the key drivers in total spending increase.
- For OASDI, the other categories appear to have a constant spending across years. This may be due to many reasons and needs to be further investigated using additional data.
- For SSI, the disabled persons appear to get the lion's share.
- For SSI, the disabled persons also appear to be the key drivers in total spending increase.
- For SSI, the other categories appear to have a constant spending across years. This may be due to many reasons and needs to be further investigated using additional data.
 
Item #9 - Comparison of increase in spending % of OASDI and SSI (for largest category) against change in % increase of US population 
- Though the percentage of population increase is trending downwards for US, the percentage of spending increase for OASDI is trending upwards.
- Could the trend in OASDI mean increase in aging population of US? The trend for OASDI needs to be analyzed further with additional data to understand the reason for it.
- Though the percentage of population increase for US is trending downwards only slightly, the percentage of spending increase for SSI is trending downwards much more significantly.
- Could the trend in SSI mean there are fewer disabled people in US? Or have many disabled people been left out of the payments? The trend for SSI needs to be analyzed further with additional data to understand the reason for it.  
  
# Course Wiki  
  
Link to DATA 512 Course Wiki - https://wiki.communitydata.cc/Human_Centered_Data_Science_(Fall_2018)

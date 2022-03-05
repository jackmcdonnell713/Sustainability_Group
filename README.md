# Sustainability & Economics

## Content

### Selected topic

Urbanization

### Reason why we selected their topic

For most of human history, people have lived in rural communities.  Only over the past few centuries have we witnessed "urbanization" or a shift from primarily low-density, rural settings dominated by agricultural production to more high-dense, urban settings.  Further, very few countries have experience exponential growth in urbanization over a short period of time like China has in recent decades.  

Despite these observations, it is expected that by 2050, more than two-thirds global population will live in urban areas. We need to understand how urbanization, and exponential growth in urbanization of select countries, impacts global demand for food and energy.  The purpose of our final project is to examine independent variables, such as human population, human population living in urban areas, GDP growth as an annual percentage, etc., in relation to metrics that measure food and energy usage.  One such dependent variable is energy consumption per capita (kWh) which is the first metric we are measuring in this week's deliverable.

This time of analysis is important for economists and professionals in the oil and agricultural sectors who will be impacted by rapid global urbanization in the next 30 years.  We expect that the demand for energy and food will increase, and long-term solutions will need to be made to offset the antropologic effects of urbanization on our planet due to deforestation for increased agriculutal land use, notably in LATAM, and increased emissions due to rising global energy demands.  Fortunately, there are renewable energy sources that can be leveraged to offset some of the effects of urbanization in the coming years.   

### Description of their source of data

For our first deliverable, our mockup databsae is comprised of four datasets which are listed below.  We expect that we will add additional dependent variables in future weeks. 

GDP : 1960 – present. 
This dataset is derived from The World Bank and measures annual GDP growth (%) by country.  The dataset was last revised in 2019.
https://data.worldbank.org/indicator/NY.GDP.MKTP.CD?locations=CN

Population : 1960 – present.  
This dataset is derived from The World Bank and measures population by country by year.  The dataset was last revised in 2019.
https://data.worldbank.org/indicator/SP.POP.TOTL?locations=CN

Urbanization data : 1960 – present.  
This dataset is derived from The World Bank and measures urbanized population by country by year.  The dataset was last revised in 2019. 
https://data.worldbank.org/indicator/SP.URB.TOTL.IN.ZS?locations=CN

Energy consumption data : 1985 - present.  
This dataset provides total energy consumption by country by year.  The term "energy consumption" here means the sum of energy used for electricity, transport and heating.
https://ourworldindata.org/energy-production-consumption


### Questions we hope to answer with the data

We would like to answer the question "how urbanization impacts demand for food and energy" by using Chinese urbanization as a case study.  Assuming key assumptions are met (ie assumptions regarding pace of urbanization, energy demands, diet of country, etc.), our Chinese demand model could be used as a proxy for similiar countries who are expected to experirence similiar, exponential growth in urbanization over a short few decades.  


## Technologies Used
### Data Cleaning and Analysis
Python and Pandas was used to read in and create dataframes for the CSV's. Then we extracted China from the 3 DataFrames and concatenate them to their own DataFrame. Once both independent and Dependent variables were created we needed to clean them once again (dropping columns with null values, Transposing the Dataframe and renaming columns).

### Database Storage
Postgres SQL will be the Database storage we used but for our mockup this week we included a folder.

### Machine Learning
Linear Regression, 
SciKitLearn ML library are the machine learning dependencies we used for our initial linear regression model.  
After looking at the mockup and thinking more about what data we want to end up using we might move to a sigmoid function as we expect exponential growth.

### Dashboard
Tableau Public will be what we use as our visualization tool as we all find the program to be intuitive and fun to use.

## Communication Protocols 
Communication primarily through Slack.  
Meeting times per the below zoom meeting schedule

Meeting Times 
- Saturday, 5 March @ 10 AM EST via zoom  
- We met this day for roughly 4 hours with all of us present and engaged.
- Tuesday, 8 March @ 6 PM CST during class

Team member roles for Week 1
Jack: X Role
Tajah: Triangle
Ashley: Circle
Thomas: Square Role

Despite assigning specific roles for week one we found it was much more productive for all members to be actively involved in each process for the first week.  We all chipped in during the data set selection, picking of technologies used, and construction of the machine learning model mockup.

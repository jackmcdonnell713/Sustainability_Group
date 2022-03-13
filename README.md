# Sustainability & Economics

### Selected topic

Urbanization & our planet!

### Reason why we selected this topic

For most of history, humans have lived in low-density, rural communities.  Only over the past few centuries have we witnessed "urbanization" or a shift from primarily low-density, rural settings dominated by agricultural production to more high-density, urban settings.  Further, very few countries have experienced exponential growth in urbanization over a short period of time like China has in recent decades.  

Despite these observations, it is expected that by 2050, more than two-thirds of the global population will live in high-density, urban areas. We need to understand how urbanization, notably exponential growth in urbanization of select countries, impacts global demand for food and energy.  The purpose of our final project is to examine independent variables, such as human population, human population living in urban areas, GDP growth as an annual percentage, etc., in relation to metrics that measure food and energy usage.  One such dependent variable is energy consumption per capita (kWh) which is the first metric we are measuring in this week's deliverable.

This analysis is important for economists and professionals in the oil, energy, and agricultural sectors who will be impacted by rapid global urbanization over the next 30 years.  We expect that the demand for energy and food will increase, and long-term solutions will need to be adopted to offset the anthropologic effects of urbanization on our planet due to deforestation for increased agricultural land use, notably in LATAM, and increased emissions due to rising global energy demands.  Fortunately, there are renewable energy sources that can be leveraged to offset some of the effects of urbanization in the coming years (i.e. renewable diesel, sustainable aviation fuel, electric cars, etc.).  This analysis will demonstrate the necessity of adopting cleaner, renewable energy sources, and the continued investment in agricultural technology which will enable the production of more food on less land, thus reducing the need for continued deforestation, especially in the rainforests of LATAM. 

### Description of our source data

For our first deliverable, our mockup database is comprised of four datasets which are listed below.  We expect that we will add additional dependent variables in future weeks. 

#### GDP : 1960 – present. 
This dataset is derived from The World Bank and measures annual GDP growth (%) by country.  The dataset was last revised in 2019.

https://data.worldbank.org/indicator/NY.GDP.MKTP.CD?locations=CN

#### Population : 1960 – present.  
This dataset is derived from The World Bank and measures population by country by year.  The dataset was last revised in 2019.

https://data.worldbank.org/indicator/SP.POP.TOTL?locations=CN

#### Urbanization : 1960 – present.  
This dataset is derived from The World Bank and measures urbanized population by country by year.  The dataset was last revised in 2019. 

https://data.worldbank.org/indicator/SP.URB.TOTL.IN.ZS?locations=CN

#### Energy consumption data : 1985 - present.  
This dataset provides total energy consumption by country by year.  The term "energy consumption" here means the sum of energy used for electricity, transport and heating.

https://ourworldindata.org/energy-production-consumption


### Questions we hope to answer with these data

We would like to answer the question "how urbanization impacts demand for food and energy" by using Chinese urbanization as a case study.  Assuming key assumptions are met (ie assumptions regarding pace of urbanization, energy demands, diet of country, etc.), our Chinese demand model could be used as a proxy for similiar countries who are expected to experience similiar, exponential growth in urbanization over a short few decades.  


## Technologies Used
### Data Cleaning and Analysis
Python and Pandas was used to read in and create dataframes for the 4 csv files (global GDP, global population, global urban population, global energy use). 

Specifically, we created 3 globa dataframes showing global GDP, global population, and global urban population by country and wear.  Next, we extracted China GDP, China population, and Chinese urban population by year from the 3 global dataframes, and then concatenated the 3 dataframes into a single China dataframe showing China GDP, China population, and China urban population by year in a single dataframe. 

We followed a similar process for our dependent variable, energy use, by first creating a global energy dataframe, then dropping non-China data from the dataframe, and then concatenating the dataframe to the dataframe containing our 3 independent variables.  

Once both independent and dependent variables were created and concatenated into a single dataframe, we did some data scrubbing (dropping columns with null values, transposing the dataframe, renaming columns, etc).

### Database Storage
Postgres SQL will be the Database storage we used but for our mockup this week we included a folder called "Resources" in our gitHub repository. This is where our provisional database is currently housed. 

### Machine Learning
We chose a supervised machine learning model, linear regression, for this analysis because our input data (GDP, population, urbanization) has a paired outcome (food demand, energy demand).  We can plug in Chinese urbanization data to train our model to predict outcomes in our India dataset.  This approach is more appropriate than unsupervised machine learning models in which there are no paired inputs and outcomes.

SciKitLearn ML library is the machine learning dependencies we used for our intial model, which is a linear regression model.  
After examining the results of the linear regression models, we decided to take a "pause" and really think about the type of analysis that we will use for our final project.  We may use a limear regression, a multivariate regression, or a multivariate multiple regression, depending on what our data is telling us to use. 

A deeper approach to this analysis would employ the use of supervised machine learning, specifically Random Forest modeling.  Random Forest modeling employees the use smaller, simpler declision trees built from a random subset of features and generally are weak learners on their own.  Collectively, however, the aggregate of these weak learners creates a powerful, robust model!  Random Forest modeling is robust against overfitting given that the weak learners are each trained on a different subset of data, are robust to both outliers and nonlinear data, and enable users to rank the importance of input variables.  At this time, we are working towards creating a Random Forest model for our analysis.  

### Dashboard
Tableau Public is what we will use as our visualization tool because we find the program to be intuitive and fun to use.

## Communication Protocols 
We have and will continue to communication primarily through Slack.  
Meeting times per the below zoom meeting schedule.

Meeting Times 
- Saturday, 5 March @ 10 AM EST via zoom  
- We met this day for roughly 4 hours with all of us present and engaged.
- Tuesday, 8 March @ 6 PM CST during class

Team member roles for Week 1

Jack: X Role

Tajah: Triangle

Ashley: Circle

Thomas: Square Role

Despite assigning specific roles for week one, we found it was much more productive for all members to be actively involved in each process for the first week.  We all chipped in during the dataset selection, picking of technologies used, and construction of the machine learning model mockup.

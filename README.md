# Sustainability & Economics

### Selected topic

Urbanization & our planet!

### Reason why we selected this topic

For most of history, humans have lived in low-density, rural communities.  Only over the past few centuries have we witnessed "urbanization" or a shift from primarily low-density, rural settings dominated by agricultural production to more high-density, urban settings.  Further, very few countries have experienced exponential growth in urbanization over a short period of time like China has in recent decades.  

Despite these observations, it is expected that by 2050, more than two-thirds of the global population will live in high-density, urban areas. We need to understand how urbanization, notably exponential growth in urbanization of select countries, impacts global demand for food and energy.  The purpose of our final project is to examine independent variables, such as human population, human population living in urban areas, GDP growth as an annual percentage, etc., in relation to metrics that measure food and energy usage.  One such dependent variable is energy consumption per capita (kWh) which is the first metric we are measuring in this week's deliverable.

This analysis is important for economists and professionals in the oil, energy, and agricultural sectors who will be impacted by rapid global urbanization over the next 30 years.  We expect that the demand for energy and food will increase, and long-term solutions will need to be adopted to offset the anthropologic effects of urbanization on our planet due to deforestation for increased agricultural land use, notably in LATAM, and increased emissions due to rising global energy demands.  Fortunately, there are renewable energy sources that can be leveraged to offset some of the effects of urbanization in the coming years (i.e. renewable diesel, sustainable aviation fuel, electric cars, etc.).  This analysis will demonstrate the necessity of adopting cleaner, renewable energy sources, and the continued investment in agricultural technology which will enable the production of more food on less land, thus reducing the need for continued deforestation, especially in the rainforests of LATAM. 

### Description of our source data

For our first deliverable, our mockup database is comprised of four datasets which are listed below.  We expect that we will add additional dependent variables in future weeks. 

#### GDP GROWTH DATA : 1960 – present. 
This dataset is derived from The World Bank and measures annual GDP growth (%) by country.  The dataset was last revised in 2019.

https://data.worldbank.org/indicator/NY.GDP.MKTP.KD.ZG?locations=CN

#### Population : 1960 – present.  
This dataset is derived from The World Bank and measures population by country by year.  The dataset was last revised in 2019.

https://data.worldbank.org/indicator/SP.POP.TOTL?locations=CN

#### Urban Population : 1960 – present.  
This dataset is derived from The World Bank and measures urbanized population by country by year.  This data measures the percentage of the total population living in Urban areas.  The dataset was last revised in 2019. 

https://data.worldbank.org/indicator/SP.URB.TOTL.IN.ZS?locations=CN

#### Energy consumption data : 1980 - present.  
This dataset provides total energy consumption by country by year, measured in quads.  "Energy consumption" includes the consumption of petroleum, dry natural gas, coal, net nuclear, hydroelectric, and non-hydroelectric renewable electricity.  Since we decided on a time serier forecast, total energy 5 yr represents the energy consumption five years forward of the current listed year.

https://www.eia.gov/international/data/country/CHN/total-energy/total-energy-consumption?pd=44&p=0000000010000000000000000000000000000000000000000000000000u06&u=0&f=A&v=mapbubble&a=-&i=none&vo=value&t=C&g=none&l=249--38&s=315532800000&e=1546300800000&


### Questions we hope to answer with these data

We would like to answer the question "how urbanization impacts demand for food and energy" by using Chinese urbanization as a case study.  Assuming key assumptions are met (ie assumptions regarding pace of urbanization, energy demands, diet of country, etc.), our Chinese demand model could be used as a proxy for similiar countries who are expected to experience similiar, exponential growth in urbanization over a short few decades.  


## Technologies Used
### Data Cleaning and Analysis
Python and Pandas was used to read in and create dataframes for the 4 csv files (global GDP, global population, global urban population, global energy use). 

Specifically, we created 3 globa dataframes showing global GDP, global population, and global urban population by country and wear.  Next, we extracted China GDP, China population, and Chinese urban population by year from the 3 global dataframes, and then concatenated the 3 dataframes into a single China dataframe showing China GDP, China population, and China urban population by year in a single dataframe. 

We followed a similar process for our dependent variable, energy use, by first creating a global energy dataframe, then dropping non-China data from the dataframe, and then concatenating the dataframe to the dataframe containing our 3 independent variables.  

Once both independent and dependent variables were created and concatenated into a single dataframe, we did some data scrubbing (dropping columns with null values, transposing the dataframe, renaming columns, etc).



### Database Storage
Postgres SQL will be the Database storage, and we used PGAdmin to manipulate or data sources. We used but for our mockup this week we included a folder called "Resources" in our gitHub repository under the folder "SQL". We showed screen shots of the table creation and joins.

Using pgAdmin, we will export our table join from Postgres SQL to a csv file that will then be used as the input for our machine learning model in Jupyter notebook.

Includes at least two tables
We created 3 tables, then thru joins combined all three tables on the yrs column - which we then exported as a csv - labeled 'testdata' and worked off of for the balance of our project


Includes at least one connection string (using SQLAlchemy or PyMongo) Note: If you use a SQL database, you must provide your ERD with relationships.
Please see the ERD below

![ERD](https://user-images.githubusercontent.com/91917546/159185623-d549e94f-03c0-479a-8ab4-54e99cc9b435.png)


### Machine Learning
We chose a supervised machine learning model, linear regression, for this analysis because our input data (GDP, urban population, urbanization) has a paired outcome (food demand, energy demand).  We can plug in Chinese urbanization data to train our model to predict outcomes in our India dataset.  This approach is more appropriate than unsupervised machine learning models in which there are no paired inputs and outcomes.

SciKitLearn ML library is the machine learning dependencies we used for our intial model, which is a linear regression model.  
After examining the results of the linear regression models, we decided to take a "pause" and really think about the type of analysis that we will use for our final project.  We may use a limear regression, a multivariate regression, or a multivariate multiple regression, depending on what our data is telling us to use. 

A deeper approach to this analysis would employ the use of supervised machine learning, specifically Random Forest modeling.  Random Forest modeling employees the use smaller, simpler declision trees built from a random subset of features and generally are weak learners on their own.  Collectively, however, the aggregate of these weak learners creates a powerful, robust model!  Random Forest modeling is robust against overfitting given that the weak learners are each trained on a different subset of data, are robust to both outliers and nonlinear data, and enable users to rank the importance of input variables.  At this time, we are working towards creating a Random Forest model for our analysis.  

During the investigative stage of the project, we learned that there is a "extrapolation problem" with using a Random Forest model.  Because of this, the random forest model assumes that predictions will fall close to the maximim value in the training dataset, as illustrated in the below image.  This is problematic if our goal is to project energy demand subsequent of India's expected, ongoing exponential urbanization.  For this reason, we are now considering using a Random Forest Regression which avoids the extrapolation problem.  

### CHANGE IN DATA SET
Our current data set, 'testdata' has changed from the aforementioned dataset.  We identfied challenges in projecting future energy demand, and as a result pivoted to a new dataset.  Our previous data set only looked at current energy consumption, and since we performed a time series forecast - we needed to relate future energy consumption (in our case 5 years forward) to our current independent variables (Year, GDP Growth and Percent of Population living in Urban Areas). While this has solved the extrapolation problem discussed above, we very likely will pivot our dataset again to utilize a more robust dataset.  We encountered issues with using too small of a dataset since we are effectively removing five rows of data due to our need to utilize energy consumption data 5 years ahead of our other independent variables.

# Issues Had within Machine Learnning DataSet 

A major issue we had with ouir initial machine learning model was that we werent't thinking about our variables correctly.  Our model was ideally supposed to predict what the future years beyond our dataset had in store energy consumption-wise for China but given our lack of understanding it would only predict values that currently existed within the data set.  Our outcome shouldn’t be the current year it should be the year 5-10 years from that variable so instead of comparing say 1980 to itself in the model the year should operate on a year 5 years in the future.  Changing the y valuable and shifting it to 5 years in the future would help us achieve our ideal Time series forecast but we have found it to be very tricky.  We may change our model again but our general ideas about what we want remain the same!

Below is a figure that better visualizes the extrapolation problem addressed earlier.




###![Figure 1: Extrapolation Problem with Random Forest](https://github.com/jackmcdonnell713/Sustainability_Group/blob/main/ExtrapolationProblem.PNG)

### Dashboard
Tableau Public is what we will use as our visualization tool because we find the program to be intuitive and fun to use.  Here is a link to our google slides that provide a brief outline for the presentation.

https://docs.google.com/presentation/d/1hcUUxudJCIKIiH2meyf5kHqM0MWkAN7eNCEKxKkjidY/edit?usp=sharing

## Communication Protocols 
We have and will continue to communicate primarily through Slack.  
Meeting times per the below zoom meeting schedule.

Meeting Times 
- Saturday, 5 March @ 10 AM EST via zoom  
- We met this day for roughly 4 hours with all of us present and engaged.
- Tuesday, 8 March @ 6 PM CST during class
- Thursday, 10 March @ 6 PM CST during class
- Tuesday, 15 March @ 6 PM CST during class
- Thursday, 17 March @ 6 PM CST during class
- Saturday, 19 March @ 130 PM CST for approx 3 hours

Team member roles for Week 1

Jack: X Role

Tajah: Triangle

Ashley: Circle

Thomas: Square Role

Despite assigning specific roles for week one, we found it was much more productive for all members to be actively involved in each process for the first week.  We all chipped in during the dataset selection, picking of technologies used, and construction of the machine learning model mockup.

Team member roles for Week 2

We opted to blend all of the shaped roles into a more cooperative strategy where every portion of the project is worked on together as a group.  With that being said, Tajah and I worked primarily on helping with data analysis for the machine learning model and the presentation aspect where Ashley dove deep into working through the code tied to our machine learning model and Thomas put in a great deal of time on our Postgres database integration.

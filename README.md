# Sustainability & Economics

### Selected topic

Urbanization & our planet!

### Reason why we selected this topic

For most of history, humans have lived in low-density, rural communities.  Only over the past few centuries have we witnessed "urbanization" or a shift from primarily low-density, rural settings dominated by agricultural production to more high-density, urban settings.  Further, very few countries have experienced exponential growth in urbanization over a short period of time like China has in recent decades.  

Despite these observations, it is expected that by 2050, more than two-thirds of the global population will live in high-density, urban areas. We need to understand how urbanization, notably exponential growth in urbanization of select countries, impacts global demand for food and energy.  The purpose of our final project is to examine independent variables, such as human population, human population living in urban areas, GDP growth as an annual percentage, etc., in relation to metrics that measure food and energy usage.  One such dependent variable is energy consumption per capita (kWh) which is the first metric we are measuring in the 1st week's deliverable.

This analysis is important for economists and professionals in the oil, energy, and agricultural sectors who will be impacted by rapid global urbanization over the next 30 years.  We expect that the demand for energy and food will increase, and long-term solutions will need to be adopted to offset the anthropologic effects of urbanization on our planet due to deforestation for increased agricultural land use, notably in LATAM, and increased emissions due to rising global energy demands.  Fortunately, there are renewable energy sources that can be leveraged to offset some of the effects of urbanization in the coming years (i.e. renewable diesel, sustainable aviation fuel, electric cars, etc.).  This analysis will demonstrate the necessity of adopting cleaner, renewable energy sources, and the continued investment in agricultural technology which will enable the production of more food on less land, thus reducing the need for continued deforestation, especially in the rainforests of LATAM. 

After testing this data it was found that projecting the next 50 years seemed to be a bit difficult. So we are interested in learning about the relationship between crude oil, alternative fuels, and factors that impact their demand and pricing. This is ever important, especially now, given Ukraine and Russia turmoil which has resulted in significantly higher and more volatile crude oil pricing. We anticipate the current increased trend towards renewable fuel sources to exacerbate due to forthcoming price shocks and volatility.  Ultimately, the slow weening of crude oil dependence and increased consumption of renewable fuel sources will lead to less anthropological destruction and negative effect - which is a cause worth fighting for.

Through discussions with several TAs and our course instructor, we learned of a more appropriate model for time series forecasting called ARIMA.  This is an ideal model for “out-of-sample” forecasting.  ARIMA is an acronym that stands for Autoregressive Integrated Moving Average.  Autoregression means that the model uses a dependent relationship between an observation and X number of lagged observations.  The I in ARIMA stands for integrated, meaning that the model utilizes difference between a single observation and the previous observation.  We found this to be particularly helpful in prediction of crude oil pricing, since the infitinte vectors and variables that come with producing a number that essentially represents the global energy consumption at any given moment we found to be near impossible to accurately quantifiy.  The RA in ARIMA stands for moving average, meaning that the model uses the dependency between an observation and the residual error from the moving average. The model's reliance on a single variable assists in accuracy since our single variable is true and absolute - though the changes are volatile.  Other independent variables like yearly crude oil consumption are hu   

There are three parameters of ARIMA, specifically (p,d,q).  P refers to the lag order, or the number of lag observations included in the model. D refers to the degree of differencing, or the number of times the raw observations are differenced.  The number of differencing parameter allows us to capitilize on a vast and uniform data set.   Q refers to the order of the moving average, or the size of the moving average window.  We posit, given an hey shit even more thorough observation of an even more robust dataset, we could become exponentially more accurate in our precision of predictability.  Each of these parameters are substituted with integers to indicate the type of ARMMA model being used.  If a zero is substituted for a parameter, that element will not be used in the ARIMA model.  

When we fit the ARIMA model to our crude oil dataset, we learned that our data was best fit to ARIMA (0,1,0) which had the smallest AIC value compared to other fits.  
![ARIMA fit]( https://github.com/AMHembrough/Final-Projcet/blob/main/Resources/ARIMA%20fit.PNG)

One limitation of ARIMA modeling, which we’ve mentioned already, is that it only utilizes a single variable.  For this reason, it’s worth noting that the VAR model - which stands for Vector Autoregression - doesn’t have this limitation, which is why we are eager to attempt as well!  We believe that with our GDP, Ubranization, and population datasets could be utilized in the VAR method to more accurately forecast crude oil data!

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

Since pivoting we have decided to use crude oil price which was obtained through Kaggle. The csv file contains crude oil daily pricing in USD from 2/3/2011 through 12/31/2019. There are 2198 rows of data, including the header row.

We also explored other variables with our ARIMA model such as sustainability index and pricing of various RIN d-codes, specifically D3, D4, D5 and D6. The sustainability data was derived from Kaggle, while the RIN pricing data were derived from the Environmental Protection Agency, or EPA.


### Questions we hope to answer with these data

We would like to answer the question "how urbanization impacts demand for food and energy" by using Chinese urbanization as a case study.  Assuming key assumptions are met (ie assumptions regarding pace of urbanization, energy demands, diet of country, etc.), our Chinese demand model could be used as a proxy for similiar countries who are expected to experience similiar, exponential growth in urbanization over a short few decades. Since it is a bit difficult to forecast future urbanization, energy and food demand with this data set we've decided to want to learn how to conduct time series analysis with “out-of-sample” forecasting via supervised machine learning, specifically ARIMA. With this we will try to project crude oil pricing.


## Technologies Used
### Data Cleaning and Analysis
Python and Pandas was used to read in and create dataframes for the 4 csv files (global GDP, global population, global urban population, global energy use). 

Specifically, we created 3 globa dataframes showing global GDP, global population, and global urban population by country and wear.  Next, we extracted China GDP, China population, and Chinese urban population by year from the 3 global dataframes, and then concatenated the 3 dataframes into a single China dataframe showing China GDP, China population, and China urban population by year in a single dataframe. 

We followed a similar process for our dependent variable, energy use, by first creating a global energy dataframe, then dropping non-China data from the dataframe, and then concatenating the dataframe to the dataframe containing our 3 independent variables.  

Once both independent and dependent variables were created and concatenated into a single dataframe, we did some data scrubbing (dropping columns with null values, transposing the dataframe, renaming columns, etc).

Prior to pivoting to our new datset we had selected several databases from World Bank and EIA which we believed would be useful in projecting China and India energy demand over time. Through the data exploration phase of the project, we learned that our datasets contained too few rows.

Within the last week, we began looking for a new dataset that would satisfying our database row needs. While we could not find the same metrics as our original dataset, we did find a related dataset containing daily crude oil pricing.

The analysis phase of the project helped us understand the strengths and weakness of several machine learning models. During this process, we explored a number of supervised machine learning models including regression analysis, random forests, regression-enhanced random forests (RERF), and autoregressive integrated moving average (ARIMA). 

The model we are presenting as our final project is the ARIMA model.  We used two metrics to assess the quality of the ARIMA model, specifically MSE and SMAPE.  
-	Mean squared error measures the difference between the predicted values and the actual values. The lesser the MSE, the closer the fit. In our model, the MSE is 1.77.
-	SMAPE was also calculated to determine model accuracy. The Symmetric Mean Absolute Percentage Error, or SMAPE, is a measurement based on percentage errors. Like MSE, the lower the value of SMAPE, the higher the model accuracy. Because SMAPE is percentage based, it’s scale-dependent and can be used compare across datasets or models. In our model, the SMAPE is 1.50%. It will be fun to compare SMAPE between this ARIMA model, and a later VAR model.

![Model Accuracy](https://github.com/AMHembrough/Final-Projcet/blob/main/Resources/Accuracy.PNG)

### Database Storage
Postgres SQL will be the Database storage, and we used PGAdmin to manipulate or data sources. We used but for our mockup this week we included a folder called "Resources" in our gitHub repository under the folder "SQL". We showed screen shots of the table creation and joins.

Using pgAdmin, we will export our table join from Postgres SQL to a csv file that will then be used as the input for our machine learning model in Jupyter notebook.

Includes at least two tables
We created 3 tables, then thru joins combined all three tables on the yrs column - which we then exported as a csv - labeled 'testdata' and worked off of for the balance of our project

Includes at least one connection string (using SQLAlchemy or PyMongo) Note: If you use a SQL database, you must provide your ERD with relationships.
Please see the ERD below

![ERD](https://user-images.githubusercontent.com/91917546/159185623-d549e94f-03c0-479a-8ab4-54e99cc9b435.png)

Moving forward with our new dataset we have still decided to use Postgres SQL as our Database storage. We created two tables in Postgres SQL using pdAdmin. The first table stores daily pricing for crude oil, and the seconds table stores daily pricing for renewable fuel D-codes D3, D4, D5, and D6.  

![Postgres Crude Table](https://github.com/AMHembrough/Final-Projcet/blob/main/Resources/Postgres%20table.PNG)

![Postgres RIN Price Table](https://github.com/AMHembrough/Final-Projcet/blob/main/Resources/Postgres%20table2.PNG)

We joined our crude oil pricing data table with our RIN D-type pricing table.  Our output was a table showing crude pricing, alongside prices for D3, D4, D5 and D6 RIN prices.

![Postgres Join](https://github.com/AMHembrough/Final-Projcet/blob/main/Resources/Postgres%20join.PNG)

![Entity Relationship Diagram](https://github.com/AMHembrough/Final-Projcet/blob/main/Resources/Entity%20relationship%20diagram.PNG)


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


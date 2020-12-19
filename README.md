# Ada Final Project

This repo contains deliverables for our creative extension of Friendship and mobility Project

We called our extension:

# It is Raining Cats and Dogs, what do you think about going out?

## Two Notebook files are included as the core of our work

    1. data_wrangling.ipynb: in which we collected and organized the data and computed deisred metrics out of the data.
    2. data_analysis.ipynb: where we tried to analyze the possible coreelations between external parameters and movement metrics prepared in data_warngling notebook.

Our extensive report is in a data story format in:

https://sim108-data.github.io/panda-pied-story/docs/

Feel free to check that at your convenience.

### *Title:*

Mobility over a Long Term Temporal Scale

### *Abstract:*

The paper focuses on three main aspects of human mobility: geographic movement, temporal dynamics, and the social network. We propose to extend the temporal dynamic treatment from just the day/weekly timescale in the paper to look at an entire year. We will enrich our dataset by adding time series data about holidays, events, and regional weather patterns. Our hypothesis is that mobility patterns are influenced by these features. We expect to see large changes for holidays and events which are planned moments for mobility while weather patterns as an unpredictable phenomenon are expected to have a different and milder influence on the movement pattern. This will allow us to understand broader temporal trends in human mobility and periodicity and the influence of environmental factors such as weather (seasons) or natural disasters. The findings of these questions could be incorporated into a more detailed and robust model of human mobility.

### *Research Questions:*

1) Is there a significant difference in travel behavior between seasons (winter/summer/spring/fall)?

2) Can we "visually" identify holidays/events/extreme weather and formulate a statistical test that distinguishes outliers?

3) How does climate variation between locations influence movement patterns (places with cold/hot climates)?

### *Proposed Datasets:*

https://simplemaps.com/data/us-cities <br/>
Dataset representing USA Cities latitude/longitude and states names. We will classify homes user by states

https://pypi.org/project/holidays/ <br/>
We will use this python package for United States holidays. 

https://www.ncdc.noaa.gov/cdo-web/webservices/v2#gettingStarted <br/>
We will use this API to pull information about weather and temperature for different regions in the United states.

### *Methods*

#### *Pre-Processing* <br/>
We plan to focus on the contiguous United States as a geographic region as a large majority of both dataset's users have a home location there. By focusing on the USA we can employ consistent datasets for the other features that we need for our study such as climate dataset.  We will draw a lat/long box around the contiguous United States (not Alaska/Hawaii) and only keep users whose home locations are within this box.

#### *Data Collection* <br/>
We use a new dataset which shows the latitude and longitude and states of 28,372 cities of the U.S. Using the library Geopanda, we plan to link each home user’s to a city using the nearest neighbor. Then, we will be able to have their respective states and compare it with the weather data set. 

We will use an API from the NOAA (National Oceanic and Atmospheric Administration) to pull weather and climate data from their API. We can pull data by weather station and also pull in the long/latitutude location of the weather station. We have been able to set up the token and request data. We may employ a similar method as with the cities to tie houses to the nearest weather station or, if possible, we can try to get weather by city or by state. 

We will use the holidays package from python to merge holidays onto the date. 

#### *New Features* <br/>
*Daily average traveled distance (scaled by user)*<br/>
We will also look at the daily average traveled distance. <br/>
*Daily movement entropy*<br/>
	Calculate movement entropy and its temporal variation in a year span.<br/>
*Daily count of check-ins (scaled by user)* <br/>
	We will number the check-ins during a day in a year span.

Given these statistics we can distinguish outlier days which we expect to be special events such as holidays. In addition, we can study the seasonal pattern of mobility. 

#### *Data Analysis* <br/>
Perform an analysis of variance to see if we find a significant difference in travel behavior in winter vs summer. This analysis can be further extended by considering the influence of regional climate (cold vs. hot).

Run an outlier detection algorithm to identify days with unusual movement characteristics. For instance, we can calculate a confidence interval for the daily average movement characteristics and employ it to distinguish the unusual days. Or we can perform clustering based on these statistics and grouping days to  holiday/event/ordinary days.

Joining the data frame containing the average daily movement features with a holiday/event/extreme weather dataset enables us to verify if national events can explain these outliers. 

### *Proposed Timeline* 
*Week 1* - Preprocess data, generate our features from the data (daily average distance, daily/weekly movement entropy), obtain outside datasets and merge at appropriate level <br/>
*Week 2* - Perform statistical analysis, build and run the outlier detection algorithm <br/>
*Week 3* - Finalize results. Writing a data story, preparing figures & graphs. <br/>
*After December 18th* - Writing script for video and making sure it is engaging

### *Organization within the Team*
*Alec:* <br/>
Week 1 will be a bit of research into setting up and properly analyzing the statistical tests and building a proper detection algorithm. Once the data is preprocessed, in week 2 will work on implementation of the tests and detection algorithm. By the end of week 2, will want to start evaluating our tests and interpreting the result from the detection model. Week 3 will be spent building charts and models for the data story. 
<br/>*Ali:*<br/> 
Week 1 will be allotted to obtaining data from other datasets and merging the acquired datasets with the current datasets. Followingly, I will work on generating features to be fed to the tests chosen for data analysis. Week2 will be working alongside Alec to implement the statistical tests. In week 3, will be plotting results to be used in the report (data story).
<br/>*Simon:* <br/>
Week 1 : Data cleaning, preprocessing, and merging datasets together. Week 2 : When week 1 tasks are done,  helping teammates on finishing obtaining data generating features or  when everything is alright starting writing the data story.
Week 3 : lead on working with Jeykll and developing the datastory.

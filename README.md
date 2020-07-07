# Movies-Extract, Transform, Load

## Overview
In this module, we performed ETL on 3 data sources to generate an SQL database of movies.
The data came in Wikipedia Articles (JSON file), Kaggle (CSV), and ratings data (CSV). After filtering, cleaning up columns, and merging data frames, we loaded our data into an SQL database. 

## Challenge
Create a function that takes in three input files and performs the ETL process. File is saved as challenge.py

## Assumptions
### 1. We need to filter movies that have both an IMDB link and a director.
Since we will need to link the dataframes using IMDB links, this will reduce the amount of data without links. 
### 2. Remove lisitngs with "No. of episodes"
If a movie entry has episodes, it is most likley a television show and should not be included in our data. 
### 3. Alternate titles can be combined. 
Some movies with multiple titles should just have one title. This will reduce the number of columns we will need.
### 4. We should assume there are probably duplicate entries. 
Becuase we have so many data points from our source data, it is possible that there are duplicates. Finding and removing any potential duplicates gives us better, more accurate data.
### 5. There are columns wil null data points. 
Some entries may have null values. If columns have over 90% of null entries, we should remove them from our dataset because they will provide superfluous information.
### 6. Some columns may not be in the same format even though they are telling us the same thing.
For instance, the release dates are presented in longform and abbreviated form. Box office earnings are n 1.2$ million or $1,200,000.
### 7. There is redundant data between our different datasets. 

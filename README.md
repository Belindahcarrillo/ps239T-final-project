# ps239T-final-project

# Short Description
For my final project I decided to use the Twitter API to investigate the way people talk (i.e. tweet) about sleep. Specifically, I was interested in understanding if the attitudes and beliefs people hold about sleep differ as a function of SES(socio-economic status). The ability to obtain quality sleep, which has downstream health consquences, is influenced by factors such as noise and air pollution, overcrowded households, and the need to work multiple jobs or jobs that shift humans natural circadian rhythms (i.e shift work). It is unsuprising that those of lower SES are more likely to experience the negative impacts of the above factors and thus sleep is a social issue. 

Using the Twitter API I was able to search tweets for key terms, such as "sleep", "tired", "exhausted", etc. and restrict my search to particular areas. I choose to focus on the five boroughs of New York City using location as a proxy for SES. Once I obtained the tweets I needed to clean it and conduct text analysis. I removed symbols and images, converted all text to lowercase, and removed punctuation.
After some tinkering I decided not to remove stop words and conduct sentiment analysis on single tokens and bigrams. Since I did not remove stopwords looking at things like simple frequency of words is not very information. Instead I decided to assign weighting to words based on how common and uncommon they are, or in other words take a token's inverse document frequency (idf). This can be combined with a token's raw frequency to calculate a term’s tf-idf (the two quantities multiplied together), the frequency of a term adjusted for how rarely it is used (Silge & Robinson, 2018). Lastly, the goal of this project was entirely exploratory with no hypothesis or predicted pattern of results. 

# Dependencies
List what software your code depends on, as well as version numbers, like so:

Access to Twitter API
R, version 3
  -Data collection scripts require the following packages
    -library(rtweet)
  -Data cleaning/analysis scripts require the following packages
    -library(tm)
    -library(SnowballC)
    -library(lubridate)
    -library(ggplot2)
    -library(dplyr)
    -library(readr)
    -library(stringr)
    -library(tidyr)

# Files
-6 csv data files
-2 R markdown files, 1 for data collection 1 for cleaning

## Data
-twitter.sleepAll.4918.csv: The New York City twitter dataset, with all boroughs combined. Variable of interest for this project include the text, plaintext, and place_full_name variables. 
  -Also included seperate files for all boroughs individually since I did collect it that way:
    -twitter.sleepMan.4918.csv (Manhattan)
    -twitter.sleepBro.4918.csv (Brooklyn)
    -twitter.sleepBron.4918.csv (Bronx)
    -twitter.sleepQue.4918.csv (Queens)
    -twitter.sleepStat.4918.csv (Staten Island)
    
## Code
01_NY_tweets-datacollection: Collects data from Twitter API, converts twitter json text to plain text and and exports data to csvs.
02_NY_tweets-datacleaning:merge-data.R: Loads, cleans, and executes exploratory analysis. 

Graphs:

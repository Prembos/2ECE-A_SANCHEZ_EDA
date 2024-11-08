# Exploratory Data Analysis
In this deliverable, you will perform an exploratory data analysis (EDA) on a dataset containing information about popular tracks on Most Streamed Spotify Songs 2023 (https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023Links to an external site.). This task aims to analyze, visualize, and interpret the data to extract meaningful insights.
## Table of Contents
  [Overview](#overview)  
  [Dependencies](#dependencies)  
  [Guide Questions](#guide-questions)  
  [Results](#results)  
  [Insights](#insights)
## Overview
#### This coding project performs data analysis on music streaming data to determine key insights such as:
- The highest number of streams
- Most popular artists
- Best-performing streaming platforms
- Trends in tracks released over time
- Patterns among tracks with same key or modes
- Artists who frequently appear in different platforms
- and more... 
## Dependencies
#### This project makes use of Jupyter Notebook and requires the following in order to work:
- numpy
- pandas
- matplotlib
- seaborn
## Guide Questions
#### In order to extract meaningful insights, several guide questions were given:
 1. Overview of Dataset
- How many rows and columns does the dataset contain?
- What are the data types of each column? Are there any missing values?
 2. Basic Descriptive Statistics
- What are the mean, median, and standard deviation of the streams column?
- What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?
 3. Top Performers
- Which track has the highest number of streams? Display the top 5 most streamed tracks.
- Who are the top 5 most frequent artists based on the number of tracks in the dataset?
  4. Temporal Trends
- Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.
- Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?
  5. Genre and Music Characteristics
- Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?
- Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?
 6. Platform Popularity
- How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare? Which platform seems to favor the most popular tracks?
 7. Advanced Analysis
- Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?
- Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.

     
## Results
#### These are the results to each guide question, retrieved through code and explained through user analysis, tables or visualization.
1. Overview of Dataset:
- The dataset contains 953 rows and 24 columns.
- The data types of each column are presented here:
  
  ![image](https://github.com/user-attachments/assets/38f91c62-96b7-4f96-9b1e-efb3ea8b1689)
  
Additionally, there are missing values. 50 in "in_shazam_charts" and 95 in "keys". For more details, please visit this [section](2ECE-A_SANCHEZ_EDA/2ECE-A_SANCHEZ_EDA.ipynb/#how-many-rows-and-columns-does-the-dataset-contain)

     

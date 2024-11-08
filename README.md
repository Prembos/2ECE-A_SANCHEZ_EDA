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
#### These are the results to each guide question, retrieved through code and explained through user analysis, tables or visualization. For details on how the program was coded, please refer to this [link](2ECE-A_SANCHEZ_EDA.ipynb#how-many-rows-and-columns-does-the-dataset-contain), or view the 2ECE-A_SANCHEZ_EDA.ipynb file.
1. Overview of Dataset:
- The dataset contains 953 rows and 24 columns.
- The data types of each column are presented here:
  
  ![image](https://github.com/user-attachments/assets/38f91c62-96b7-4f96-9b1e-efb3ea8b1689)
  
Additionally, there are missing values: 50 missing values in the "in_shazam_charts" column and 95 missing values in the "keys" column. For more details, please visit this [section](2ECE-A_SANCHEZ_EDA.ipynb#what-are-the-data-types-of-each-column?-are-there-any-missing-values?.).

2. Basic Descriptive Statistics:
- This section presents the mean, median, and standard deviation of the streams data:

  ![image](https://github.com/user-attachments/assets/737803a6-6801-4b01-8491-e2752b116968)

- The majority of tracks on the platform were released between 2021 and 2023, with a significant peak in 2022. Most tracks feature a single artist, though there are a few tracks with multiple artists, and in rare cases, there are up to eight artists.

  ![image](https://github.com/user-attachments/assets/eea80757-bb6e-4cf3-a25e-f673b1980491)

- As previously discussed, the most popular tracks on streaming platforms are from 2022, with some tracks from the years 2010 to 2023. The data also reveals that older tracks continue to be present on these platforms. When it comes to artists, most tracks feature one or two artists, though there are some tracks with three or more, with occasional instances of tracks featuring four or more artists.

  ![image](https://github.com/user-attachments/assets/16ec7af0-43e5-4354-85d4-300c2fda3010)

For more detailed information, this [link](2ECE-A_SANCHEZ_EDA.ipynb#basic-descriptive-statistics) will lead you to that section in the code.

3. Top Performers
- The top five tracks are as follows:

  ![image](https://github.com/user-attachments/assets/6bbf103b-5697-4f5f-8add-dd7fa3510b89)

- And here are the five artists that appeared most based on amount of tracks:

  ![image](https://github.com/user-attachments/assets/42daac32-b763-4e17-91a2-dc6f2b44aac5)

Here's the [link](2ECE-A_SANCHEZ_EDA.ipynb#top-performers) to this section of codes.

4. Temporal Trends
- The year 2022 stands out as the top year for track releases on this platform. Moreover, tracks are most frequently released in January and May, with over 100 tracks in each of these months. The other months have fewer than 100 releases. Interestingly, artists tend to favor the first day of each month for track releases, with this day seeing more than twice as many releases as the next most popular day. For more details on this section, visit [here](2ECE-A_SANCHEZ_EDA.ipynb#temporal-trends).

![image](https://github.com/user-attachments/assets/40bbe155-9545-46a5-a1a4-2b60d7f337e3)

5. Genre and Music Characteristics
- All of them have negligible correlation with the highest between danceability and energy at 0.20 which is still very low. The attribute that influences streams the most is danceability with approximately -0.11 which is considered negligible. For valence and acousticness, there is negligible correlation. Here's the [evidence](2ECE-A_SANCHEZ_EDA.ipynb#genre-and-music-characteristics).

  ![image](https://github.com/user-attachments/assets/d9316b75-674e-4211-8bcb-29b853423118)

6. Platform Popularity
- Spotify is the clear winner with a whopping 4,955,719 tracks. Deezer is next in line with 367,084 tracks and Apple with 64625 tracks only. Down below is a pie chart showing the [distribution of tracks across platforms](2ECE-A_SANCHEZ_EDA.ipynb#platform-popularity) is preferred over the other:

  ![image](https://github.com/user-attachments/assets/ba8fd6a6-32c3-439a-b122-395de75c86c8)

7. Advanced Analysis
- Major modes tend to have more streams with a ratio of 8:3. The only keys where the minor modes win were B, F and just barely A. By default, major modes tend to have more popular trends, but some of the outliers in each mode may have a slightly different result.

  ![image](https://github.com/user-attachments/assets/39f14463-b443-42f2-915d-24ea087d0c3d)
  ![image](https://github.com/user-attachments/assets/94f43be4-6d76-4133-ba01-407753e92584)

- Leading the list for the most playlist appearances is The Weeknd, with approximately 155,000 total appearances. Ed Sheeran follows closely in second with around 150,000, and Taylor Swift secures third with roughly 140,000 appearances. When it comes to chart appearances, the top three remain the same but in a different order: Taylor Swift takes first place, followed by The Weeknd in second, and Ed Sheeran in third. Other artists follow closely behind these top three. To refer to this section, click [here](2ECE-A_SANCHEZ_EDA.ipynb#advanced-analysis).

  ![image](https://github.com/user-attachments/assets/e147e891-8e29-4257-bb57-55426dfb81e9)






 


     

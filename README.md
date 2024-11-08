# Exploratory Data Analysis
In this deliverable, you will perform an exploratory data analysis (EDA) on a dataset containing information about popular tracks on Most Streamed Spotify Songs 2023 (https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023Links to an external site.). This task aims to analyze, visualize, and interpret the data to extract meaningful insights.
## Table of Contents
  [Overview](#overview)  
  [Dependencies](#dependencies)  
  [Guide Questions](#guide-questions)  
  [Results](#results)  
  [Summary](#summary)
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
#### Below are the results for each guide question, derived through code and explained using tables and visualizations. For detailed code explanations, please refer to this [link](2ECE-A_SANCHEZ_EDA.ipynb#how-many-rows-and-columns-does-the-dataset-contain) or view the full Jupyter notebook (2ECE-A_SANCHEZ_EDA.ipynb). As linking sections within the .ipynb file on GitHub can be inconsistent, you can find each section by searching for its name using Ctrl + F.
1. Overview of Dataset:
- The dataset contains 953 rows and 24 columns, with 50 missing values in the "in_shazam_charts" column and 95 missing values in the "keys" column. These missing values may or may not affect results containing these assets.
- The data types of each column are displayed below:
  
  ![image](https://github.com/user-attachments/assets/38f91c62-96b7-4f96-9b1e-efb3ea8b1689)
  
2. Basic Descriptive Statistics:
- This section presents the mean, median, and standard deviation of the streams data:

  ![image](https://github.com/user-attachments/assets/737803a6-6801-4b01-8491-e2752b116968)

- Most tracks on the platform were released between 2021 and 2023, with a significant peak in 2022. The majority of tracks feature a single artist, but there are a few with multiple artists, and in rare cases, tracks feature up to eight artists.

  ![image](https://github.com/user-attachments/assets/eea80757-bb6e-4cf3-a25e-f673b1980491)

- As previously mentioned, the most popular tracks come from 2022, though some tracks from 2010 to 2023 also appear. Older tracks remain on the platform. The data shows that most tracks have one or two artists, with some featuring up to three or more, and occasionally, tracks have four or more artists.

  ![image](https://github.com/user-attachments/assets/16ec7af0-43e5-4354-85d4-300c2fda3010)

3. Top Performers
- The top five tracks based on streams are as follows:

  ![image](https://github.com/user-attachments/assets/6bbf103b-5697-4f5f-8add-dd7fa3510b89)

- And here are the five artists that appeared most based on amount of tracks:

  ![image](https://github.com/user-attachments/assets/42daac32-b763-4e17-91a2-dc6f2b44aac5)

4. Temporal Trends
- The year 2022 stands out as the top year for track releases on this platform. Moreover, tracks are most frequently released in January and May, with over 100 tracks in each of these months. The other months have fewer than 100 releases. Interestingly, artists tend to favor the first day of each month for track releases, with this day seeing more than twice as many releases as the next most popular day. One interpretation of the results show that releasing on the first day of a month may be a popular marketing strategy leading to more views.

![image](https://github.com/user-attachments/assets/40bbe155-9545-46a5-a1a4-2b60d7f337e3)

5. Genre and Music Characteristics
- The correlations between genre features and streams are generally negligible, with the highest correlation being 0.20 between danceability and energy. Danceability is the feature that influences streams the most, with a -0.11 correlation. As for valence and acousticness, they also show negligible correlation with streams. The data provides evidence that these specific genre features are not responsible for increasing or decreasing streams as they have negligible correlation.

  ![image](https://github.com/user-attachments/assets/d9316b75-674e-4211-8bcb-29b853423118)

6. Platform Popularity
- Spotify is the clear leader with 4,955,719 tracks. Deezer follows with 367,084 tracks, and Apple comes in last with just 64,625 tracks. The pie chart below shows the distribution of tracks across platforms. Ultimately, this proves that Spotify is the superior option when picking a platform for listening to a variety of good music due to the amount of tracks to pick from.

  ![image](https://github.com/user-attachments/assets/ba8fd6a6-32c3-439a-b122-395de75c86c8)

7. Advanced Analysis
- Major modes tend to have more streams, with a ratio of 8:3. The only keys where minor modes outperform major modes are B, F, and just barely A. While major modes dominate overall, there are a few outliers where the minor mode may have a slightly higher stream count. This hints that people may slightly prefer tracks with major modes which may impact marketing strategies as streaming platforms can tailor their strategies to enhance listener satisfaction and engagement, potentially leading to higher retention and platform loyalty.
  ![image](https://github.com/user-attachments/assets/39f14463-b443-42f2-915d-24ea087d0c3d)
  ![image](https://github.com/user-attachments/assets/94f43be4-6d76-4133-ba01-407753e92584)

- The Weeknd takes the top spot for most appearances in playlists with 155,000 appearances, followed by Ed Sheeran with 150,000, and Taylor Swift with 140,000. For chart appearances, the top three remain the same, but in a different order: Taylor Swift is first, followed by The Weeknd and Ed Sheeran in second and third place, respectively. The rankings do not lie, it shows that listeners prefer these artists' type of music and utilizing this information could impact marketing strategies for reasons above.

  ![image](https://github.com/user-attachments/assets/e147e891-8e29-4257-bb57-55426dfb81e9)

## Summary
This analysis of the Most Streamed Spotify Songs 2023 dataset provides valuable insights into various aspects of popular music, such as rankings of the top songs, most popular artists, dominant genres, correlations between genres and streaming success, optimal release timing, and more. By understanding these elements, different stakeholders can make strategic decisions. For instance:

Listeners can discover new music tailored to their taste by identifying trending genres and popular artists.
Artists may choose when to release new music and tailor it to audience preferences, potentially increasing engagement.
Streaming Platforms can adjust recommendations and marketing strategies to align with trends and maximize user satisfaction.

As an example, tracks released on the first day of a month may perform better due to factors such as streaming algorithms, the timing of audience paychecks, consistent release schedules, and chart advantages. However, limitations exist, including the need for more recent data and the potential to refine insights by analyzing trends over specific timeframes.

In conclusion, data analysis offers a powerful tool for understanding and leveraging trends in the music industry, driving better outcomes and enhancing engagement across the board.





 


     

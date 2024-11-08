```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from IPython.display import display
```

### Overview of Dataset
#### How many rows and columns does the dataset contain?


```python
#Reads the CSV file, encoding is set in ISO-8859-1 as UTF-8 will cause errors.
df = pd.read_csv('spotify-2023.csv', encoding='ISO-8859-1')
df     #It displays here that the rows and columns are 953 x 24.
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>track_name</th>
      <th>artist(s)_name</th>
      <th>artist_count</th>
      <th>released_year</th>
      <th>released_month</th>
      <th>released_day</th>
      <th>in_spotify_playlists</th>
      <th>in_spotify_charts</th>
      <th>streams</th>
      <th>in_apple_playlists</th>
      <th>...</th>
      <th>bpm</th>
      <th>key</th>
      <th>mode</th>
      <th>danceability_%</th>
      <th>valence_%</th>
      <th>energy_%</th>
      <th>acousticness_%</th>
      <th>instrumentalness_%</th>
      <th>liveness_%</th>
      <th>speechiness_%</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Seven (feat. Latto) (Explicit Ver.)</td>
      <td>Latto, Jung Kook</td>
      <td>2</td>
      <td>2023</td>
      <td>7</td>
      <td>14</td>
      <td>553</td>
      <td>147</td>
      <td>141381703</td>
      <td>43</td>
      <td>...</td>
      <td>125</td>
      <td>B</td>
      <td>Major</td>
      <td>80</td>
      <td>89</td>
      <td>83</td>
      <td>31</td>
      <td>0</td>
      <td>8</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>LALA</td>
      <td>Myke Towers</td>
      <td>1</td>
      <td>2023</td>
      <td>3</td>
      <td>23</td>
      <td>1474</td>
      <td>48</td>
      <td>133716286</td>
      <td>48</td>
      <td>...</td>
      <td>92</td>
      <td>C#</td>
      <td>Major</td>
      <td>71</td>
      <td>61</td>
      <td>74</td>
      <td>7</td>
      <td>0</td>
      <td>10</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vampire</td>
      <td>Olivia Rodrigo</td>
      <td>1</td>
      <td>2023</td>
      <td>6</td>
      <td>30</td>
      <td>1397</td>
      <td>113</td>
      <td>140003974</td>
      <td>94</td>
      <td>...</td>
      <td>138</td>
      <td>F</td>
      <td>Major</td>
      <td>51</td>
      <td>32</td>
      <td>53</td>
      <td>17</td>
      <td>0</td>
      <td>31</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Cruel Summer</td>
      <td>Taylor Swift</td>
      <td>1</td>
      <td>2019</td>
      <td>8</td>
      <td>23</td>
      <td>7858</td>
      <td>100</td>
      <td>800840817</td>
      <td>116</td>
      <td>...</td>
      <td>170</td>
      <td>A</td>
      <td>Major</td>
      <td>55</td>
      <td>58</td>
      <td>72</td>
      <td>11</td>
      <td>0</td>
      <td>11</td>
      <td>15</td>
    </tr>
    <tr>
      <th>4</th>
      <td>WHERE SHE GOES</td>
      <td>Bad Bunny</td>
      <td>1</td>
      <td>2023</td>
      <td>5</td>
      <td>18</td>
      <td>3133</td>
      <td>50</td>
      <td>303236322</td>
      <td>84</td>
      <td>...</td>
      <td>144</td>
      <td>A</td>
      <td>Minor</td>
      <td>65</td>
      <td>23</td>
      <td>80</td>
      <td>14</td>
      <td>63</td>
      <td>11</td>
      <td>6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>948</th>
      <td>My Mind &amp; Me</td>
      <td>Selena Gomez</td>
      <td>1</td>
      <td>2022</td>
      <td>11</td>
      <td>3</td>
      <td>953</td>
      <td>0</td>
      <td>91473363</td>
      <td>61</td>
      <td>...</td>
      <td>144</td>
      <td>A</td>
      <td>Major</td>
      <td>60</td>
      <td>24</td>
      <td>39</td>
      <td>57</td>
      <td>0</td>
      <td>8</td>
      <td>3</td>
    </tr>
    <tr>
      <th>949</th>
      <td>Bigger Than The Whole Sky</td>
      <td>Taylor Swift</td>
      <td>1</td>
      <td>2022</td>
      <td>10</td>
      <td>21</td>
      <td>1180</td>
      <td>0</td>
      <td>121871870</td>
      <td>4</td>
      <td>...</td>
      <td>166</td>
      <td>F#</td>
      <td>Major</td>
      <td>42</td>
      <td>7</td>
      <td>24</td>
      <td>83</td>
      <td>1</td>
      <td>12</td>
      <td>6</td>
    </tr>
    <tr>
      <th>950</th>
      <td>A Veces (feat. Feid)</td>
      <td>Feid, Paulo Londra</td>
      <td>2</td>
      <td>2022</td>
      <td>11</td>
      <td>3</td>
      <td>573</td>
      <td>0</td>
      <td>73513683</td>
      <td>2</td>
      <td>...</td>
      <td>92</td>
      <td>C#</td>
      <td>Major</td>
      <td>80</td>
      <td>81</td>
      <td>67</td>
      <td>4</td>
      <td>0</td>
      <td>8</td>
      <td>6</td>
    </tr>
    <tr>
      <th>951</th>
      <td>En La De Ella</td>
      <td>Feid, Sech, Jhayco</td>
      <td>3</td>
      <td>2022</td>
      <td>10</td>
      <td>20</td>
      <td>1320</td>
      <td>0</td>
      <td>133895612</td>
      <td>29</td>
      <td>...</td>
      <td>97</td>
      <td>C#</td>
      <td>Major</td>
      <td>82</td>
      <td>67</td>
      <td>77</td>
      <td>8</td>
      <td>0</td>
      <td>12</td>
      <td>5</td>
    </tr>
    <tr>
      <th>952</th>
      <td>Alone</td>
      <td>Burna Boy</td>
      <td>1</td>
      <td>2022</td>
      <td>11</td>
      <td>4</td>
      <td>782</td>
      <td>2</td>
      <td>96007391</td>
      <td>27</td>
      <td>...</td>
      <td>90</td>
      <td>E</td>
      <td>Minor</td>
      <td>61</td>
      <td>32</td>
      <td>67</td>
      <td>15</td>
      <td>0</td>
      <td>11</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
<p>953 rows × 24 columns</p>
</div>



#### What are the data types of each column? Are there any missing values?


```python
df.info()     #gives info of dataframe, in here we can deduce the datatypes of each column
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 953 entries, 0 to 952
    Data columns (total 24 columns):
     #   Column                Non-Null Count  Dtype 
    ---  ------                --------------  ----- 
     0   track_name            953 non-null    object
     1   artist(s)_name        953 non-null    object
     2   artist_count          953 non-null    int64 
     3   released_year         953 non-null    int64 
     4   released_month        953 non-null    int64 
     5   released_day          953 non-null    int64 
     6   in_spotify_playlists  953 non-null    int64 
     7   in_spotify_charts     953 non-null    int64 
     8   streams               953 non-null    object
     9   in_apple_playlists    953 non-null    int64 
     10  in_apple_charts       953 non-null    int64 
     11  in_deezer_playlists   953 non-null    object
     12  in_deezer_charts      953 non-null    int64 
     13  in_shazam_charts      903 non-null    object
     14  bpm                   953 non-null    int64 
     15  key                   858 non-null    object
     16  mode                  953 non-null    object
     17  danceability_%        953 non-null    int64 
     18  valence_%             953 non-null    int64 
     19  energy_%              953 non-null    int64 
     20  acousticness_%        953 non-null    int64 
     21  instrumentalness_%    953 non-null    int64 
     22  liveness_%            953 non-null    int64 
     23  speechiness_%         953 non-null    int64 
    dtypes: int64(17), object(7)
    memory usage: 178.8+ KB
    


```python
int64_df = df.select_dtypes(include="int64")   #All int64 datatypes will be shown when called
object_df = df.select_dtypes(include="object")  #All object datatypes will be shown when called
```


```python
int64_df 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>artist_count</th>
      <th>released_year</th>
      <th>released_month</th>
      <th>released_day</th>
      <th>in_spotify_playlists</th>
      <th>in_spotify_charts</th>
      <th>in_apple_playlists</th>
      <th>in_apple_charts</th>
      <th>in_deezer_charts</th>
      <th>bpm</th>
      <th>danceability_%</th>
      <th>valence_%</th>
      <th>energy_%</th>
      <th>acousticness_%</th>
      <th>instrumentalness_%</th>
      <th>liveness_%</th>
      <th>speechiness_%</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>2023</td>
      <td>7</td>
      <td>14</td>
      <td>553</td>
      <td>147</td>
      <td>43</td>
      <td>263</td>
      <td>10</td>
      <td>125</td>
      <td>80</td>
      <td>89</td>
      <td>83</td>
      <td>31</td>
      <td>0</td>
      <td>8</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>2023</td>
      <td>3</td>
      <td>23</td>
      <td>1474</td>
      <td>48</td>
      <td>48</td>
      <td>126</td>
      <td>14</td>
      <td>92</td>
      <td>71</td>
      <td>61</td>
      <td>74</td>
      <td>7</td>
      <td>0</td>
      <td>10</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>2023</td>
      <td>6</td>
      <td>30</td>
      <td>1397</td>
      <td>113</td>
      <td>94</td>
      <td>207</td>
      <td>14</td>
      <td>138</td>
      <td>51</td>
      <td>32</td>
      <td>53</td>
      <td>17</td>
      <td>0</td>
      <td>31</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>2019</td>
      <td>8</td>
      <td>23</td>
      <td>7858</td>
      <td>100</td>
      <td>116</td>
      <td>207</td>
      <td>12</td>
      <td>170</td>
      <td>55</td>
      <td>58</td>
      <td>72</td>
      <td>11</td>
      <td>0</td>
      <td>11</td>
      <td>15</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>2023</td>
      <td>5</td>
      <td>18</td>
      <td>3133</td>
      <td>50</td>
      <td>84</td>
      <td>133</td>
      <td>15</td>
      <td>144</td>
      <td>65</td>
      <td>23</td>
      <td>80</td>
      <td>14</td>
      <td>63</td>
      <td>11</td>
      <td>6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>948</th>
      <td>1</td>
      <td>2022</td>
      <td>11</td>
      <td>3</td>
      <td>953</td>
      <td>0</td>
      <td>61</td>
      <td>13</td>
      <td>1</td>
      <td>144</td>
      <td>60</td>
      <td>24</td>
      <td>39</td>
      <td>57</td>
      <td>0</td>
      <td>8</td>
      <td>3</td>
    </tr>
    <tr>
      <th>949</th>
      <td>1</td>
      <td>2022</td>
      <td>10</td>
      <td>21</td>
      <td>1180</td>
      <td>0</td>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>166</td>
      <td>42</td>
      <td>7</td>
      <td>24</td>
      <td>83</td>
      <td>1</td>
      <td>12</td>
      <td>6</td>
    </tr>
    <tr>
      <th>950</th>
      <td>2</td>
      <td>2022</td>
      <td>11</td>
      <td>3</td>
      <td>573</td>
      <td>0</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>92</td>
      <td>80</td>
      <td>81</td>
      <td>67</td>
      <td>4</td>
      <td>0</td>
      <td>8</td>
      <td>6</td>
    </tr>
    <tr>
      <th>951</th>
      <td>3</td>
      <td>2022</td>
      <td>10</td>
      <td>20</td>
      <td>1320</td>
      <td>0</td>
      <td>29</td>
      <td>26</td>
      <td>0</td>
      <td>97</td>
      <td>82</td>
      <td>67</td>
      <td>77</td>
      <td>8</td>
      <td>0</td>
      <td>12</td>
      <td>5</td>
    </tr>
    <tr>
      <th>952</th>
      <td>1</td>
      <td>2022</td>
      <td>11</td>
      <td>4</td>
      <td>782</td>
      <td>2</td>
      <td>27</td>
      <td>18</td>
      <td>1</td>
      <td>90</td>
      <td>61</td>
      <td>32</td>
      <td>67</td>
      <td>15</td>
      <td>0</td>
      <td>11</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
<p>953 rows × 17 columns</p>
</div>




```python
object_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>track_name</th>
      <th>artist(s)_name</th>
      <th>streams</th>
      <th>in_deezer_playlists</th>
      <th>in_shazam_charts</th>
      <th>key</th>
      <th>mode</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Seven (feat. Latto) (Explicit Ver.)</td>
      <td>Latto, Jung Kook</td>
      <td>141381703</td>
      <td>45</td>
      <td>826</td>
      <td>B</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>1</th>
      <td>LALA</td>
      <td>Myke Towers</td>
      <td>133716286</td>
      <td>58</td>
      <td>382</td>
      <td>C#</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vampire</td>
      <td>Olivia Rodrigo</td>
      <td>140003974</td>
      <td>91</td>
      <td>949</td>
      <td>F</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Cruel Summer</td>
      <td>Taylor Swift</td>
      <td>800840817</td>
      <td>125</td>
      <td>548</td>
      <td>A</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>4</th>
      <td>WHERE SHE GOES</td>
      <td>Bad Bunny</td>
      <td>303236322</td>
      <td>87</td>
      <td>425</td>
      <td>A</td>
      <td>Minor</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>948</th>
      <td>My Mind &amp; Me</td>
      <td>Selena Gomez</td>
      <td>91473363</td>
      <td>37</td>
      <td>0</td>
      <td>A</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>949</th>
      <td>Bigger Than The Whole Sky</td>
      <td>Taylor Swift</td>
      <td>121871870</td>
      <td>8</td>
      <td>0</td>
      <td>F#</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>950</th>
      <td>A Veces (feat. Feid)</td>
      <td>Feid, Paulo Londra</td>
      <td>73513683</td>
      <td>7</td>
      <td>0</td>
      <td>C#</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>951</th>
      <td>En La De Ella</td>
      <td>Feid, Sech, Jhayco</td>
      <td>133895612</td>
      <td>17</td>
      <td>0</td>
      <td>C#</td>
      <td>Major</td>
    </tr>
    <tr>
      <th>952</th>
      <td>Alone</td>
      <td>Burna Boy</td>
      <td>96007391</td>
      <td>32</td>
      <td>0</td>
      <td>E</td>
      <td>Minor</td>
    </tr>
  </tbody>
</table>
<p>953 rows × 7 columns</p>
</div>




```python
#0 means no missing value, numbers means there is a missing value pertaining to that amount, indicating that in_shazam_charts and key have 50 and 95 missing values respectively.
df.isnull().sum()     #.isnull() checks if an element has a missing value (NaN), .sum() counts the number of true values in each column and summarizes.
```




    track_name               0
    artist(s)_name           0
    artist_count             0
    released_year            0
    released_month           0
    released_day             0
    in_spotify_playlists     0
    in_spotify_charts        0
    streams                  0
    in_apple_playlists       0
    in_apple_charts          0
    in_deezer_playlists      0
    in_deezer_charts         0
    in_shazam_charts        50
    bpm                      0
    key                     95
    mode                     0
    danceability_%           0
    valence_%                0
    energy_%                 0
    acousticness_%           0
    instrumentalness_%       0
    liveness_%               0
    speechiness_%            0
    dtype: int64



### Basic Descriptive Statistics
#### What are the mean, median, and standard deviation of the streams column?


```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>artist_count</th>
      <th>released_year</th>
      <th>released_month</th>
      <th>released_day</th>
      <th>in_spotify_playlists</th>
      <th>in_spotify_charts</th>
      <th>in_apple_playlists</th>
      <th>in_apple_charts</th>
      <th>in_deezer_charts</th>
      <th>bpm</th>
      <th>danceability_%</th>
      <th>valence_%</th>
      <th>energy_%</th>
      <th>acousticness_%</th>
      <th>instrumentalness_%</th>
      <th>liveness_%</th>
      <th>speechiness_%</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.00000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
      <td>953.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.556139</td>
      <td>2018.238195</td>
      <td>6.033578</td>
      <td>13.930745</td>
      <td>5200.124869</td>
      <td>12.009444</td>
      <td>67.812172</td>
      <td>51.908709</td>
      <td>2.666317</td>
      <td>122.540399</td>
      <td>66.96957</td>
      <td>51.431270</td>
      <td>64.279119</td>
      <td>27.057712</td>
      <td>1.581322</td>
      <td>18.213012</td>
      <td>10.131165</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.893044</td>
      <td>11.116218</td>
      <td>3.566435</td>
      <td>9.201949</td>
      <td>7897.608990</td>
      <td>19.575992</td>
      <td>86.441493</td>
      <td>50.630241</td>
      <td>6.035599</td>
      <td>28.057802</td>
      <td>14.63061</td>
      <td>23.480632</td>
      <td>16.550526</td>
      <td>25.996077</td>
      <td>8.409800</td>
      <td>13.711223</td>
      <td>9.912888</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>1930.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>31.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>65.000000</td>
      <td>23.00000</td>
      <td>4.000000</td>
      <td>9.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>3.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1.000000</td>
      <td>2020.000000</td>
      <td>3.000000</td>
      <td>6.000000</td>
      <td>875.000000</td>
      <td>0.000000</td>
      <td>13.000000</td>
      <td>7.000000</td>
      <td>0.000000</td>
      <td>100.000000</td>
      <td>57.00000</td>
      <td>32.000000</td>
      <td>53.000000</td>
      <td>6.000000</td>
      <td>0.000000</td>
      <td>10.000000</td>
      <td>4.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.000000</td>
      <td>2022.000000</td>
      <td>6.000000</td>
      <td>13.000000</td>
      <td>2224.000000</td>
      <td>3.000000</td>
      <td>34.000000</td>
      <td>38.000000</td>
      <td>0.000000</td>
      <td>121.000000</td>
      <td>69.00000</td>
      <td>51.000000</td>
      <td>66.000000</td>
      <td>18.000000</td>
      <td>0.000000</td>
      <td>12.000000</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2.000000</td>
      <td>2022.000000</td>
      <td>9.000000</td>
      <td>22.000000</td>
      <td>5542.000000</td>
      <td>16.000000</td>
      <td>88.000000</td>
      <td>87.000000</td>
      <td>2.000000</td>
      <td>140.000000</td>
      <td>78.00000</td>
      <td>70.000000</td>
      <td>77.000000</td>
      <td>43.000000</td>
      <td>0.000000</td>
      <td>24.000000</td>
      <td>11.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>8.000000</td>
      <td>2023.000000</td>
      <td>12.000000</td>
      <td>31.000000</td>
      <td>52898.000000</td>
      <td>147.000000</td>
      <td>672.000000</td>
      <td>275.000000</td>
      <td>58.000000</td>
      <td>206.000000</td>
      <td>96.00000</td>
      <td>97.000000</td>
      <td>97.000000</td>
      <td>97.000000</td>
      <td>91.000000</td>
      <td>97.000000</td>
      <td>64.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Change datatype of 'streams' to numeric to get its mean, median and std. Only works once, doing it again would result in an error as these objects would already be converted to strings.
df['streams'] = pd.to_numeric(df['streams'].str.replace(',', ''), errors='coerce')     
df['in_deezer_playlists'] = pd.to_numeric(df['in_deezer_playlists'].str.replace(',', ''), errors='coerce')
df['in_shazam_charts'] = pd.to_numeric(df['in_shazam_charts'].str.replace(',', ''), errors='coerce')
df.loc[:,['streams']].agg(['mean','median','std'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>streams</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>mean</th>
      <td>5.141374e+08</td>
    </tr>
    <tr>
      <th>median</th>
      <td>2.905309e+08</td>
    </tr>
    <tr>
      <th>std</th>
      <td>5.668569e+08</td>
    </tr>
  </tbody>
</table>
</div>



#### What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?


```python
# Count occurrences of each released year and artist count to filter out years with no occurrences
released_year_unique = df['released_year'].value_counts().sort_index()
artist_count_unique = df['artist_count'].value_counts().sort_index()

# Create a figure with subplots for both bar plots
fig, axs = plt.subplots(2, 1, figsize=(12, 12))

# Bar plot for released_year
sns.barplot(x=released_year_unique.index, y=released_year_unique.values, ax=axs[0], palette='Blues')
axs[0].set_title('Distribution of Released Year')
axs[0].set_xlabel('Year Released')
axs[0].set_ylabel('Count')
axs[0].tick_params(axis='x', rotation=45)

# Bar plot for artist_count
sns.barplot(x=artist_count_unique.index, y=artist_count_unique.values, ax=axs[1], palette='RdYlBu')
axs[1].set_title('Distribution of Artist Count')
axs[1].set_xlabel('Number of Artists per Track')
axs[1].set_ylabel('Count')
axs[1].tick_params(axis='x')

plt.tight_layout()
plt.show()
```

    C:\Users\PC1\AppData\Local\Temp\ipykernel_5580\4226140516.py:9: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x=released_year_unique.index, y=released_year_unique.values, ax=axs[0], palette='Blues')
    C:\Users\PC1\AppData\Local\Temp\ipykernel_5580\4226140516.py:16: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x=artist_count_unique.index, y=artist_count_unique.values, ax=axs[1], palette='RdYlBu')
    


    
![png](output_13_1.png)
    



```python
# Create a figure with subplots for box plots
fig, axs = plt.subplots(2, 1, figsize=(8, 8))

# Box plot for released_year
sns.boxplot(x=df['released_year'], ax=axs[0])
axs[0].set_title('Trends in Released Year')
axs[0].set_xlabel('Released Year')

# Box plot for artist_count
sns.boxplot(x=df['artist_count'], ax=axs[1])
axs[1].set_title('Trends in Artist Count')
axs[1].set_xlabel('Artist Count')

# Show the plots
plt.tight_layout()
plt.show()
```


    
![png](output_14_0.png)
    


### Top Performers
#### Which track has the highest number of streams? Display the top 5 most streamed tracks.


```python
df.sort_values(by='streams', ascending=False)[['track_name','streams']].head() #'Streams' were converted to numeric values earlier, sort values to descending order then display the top 5.
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>track_name</th>
      <th>streams</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>55</th>
      <td>Blinding Lights</td>
      <td>3.703895e+09</td>
    </tr>
    <tr>
      <th>179</th>
      <td>Shape of You</td>
      <td>3.562544e+09</td>
    </tr>
    <tr>
      <th>86</th>
      <td>Someone You Loved</td>
      <td>2.887242e+09</td>
    </tr>
    <tr>
      <th>620</th>
      <td>Dance Monkey</td>
      <td>2.864792e+09</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Sunflower - Spider-Man: Into the Spider-Verse</td>
      <td>2.808097e+09</td>
    </tr>
  </tbody>
</table>
</div>



#### Who are the top 5 most frequent artists based on the number of tracks in the dataset?


```python
df['artist(s)_name'].value_counts().head()
```




    artist(s)_name
    Taylor Swift    34
    The Weeknd      22
    Bad Bunny       19
    SZA             19
    Harry Styles    17
    Name: count, dtype: int64



### Temporal Trends
#### Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.
#### Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?


```python
# Count occurrences
released_year_counts = df['released_year'].value_counts().sort_index()
released_month_counts = df['released_month'].value_counts().sort_index()
released_day_counts = df['released_day'].value_counts().sort_index()

# Create a figure for the bar plots
fig, axs = plt.subplots(3, 1, figsize=(12, 18))

# Bar plot for released_year
sns.barplot(x=released_year_counts.index, y=released_year_counts.values, palette='viridis', ax=axs[0])
axs[0].set_title('Number of Tracks Released Per Year')
axs[0].set_xlabel('Year Released')
axs[0].set_ylabel('Number of Tracks')
axs[0].tick_params(axis='x', rotation=45)

# Bar plot for released_month
sns.barplot(x=released_month_counts.index, y=released_month_counts.values, palette='Spectral', ax=axs[1])
axs[1].set_title('Number of Tracks Released Per Month')
axs[1].set_xlabel('Month Released')
axs[1].set_ylabel('Number of Tracks')
axs[1].tick_params(axis='x')

# Bar plot for released_day
sns.barplot(x=released_day_counts.index, y=released_day_counts.values, palette='RdYlBu', ax=axs[2])
axs[2].set_title('Number of Tracks Released Per Day')
axs[2].set_xlabel('Day Released')
axs[2].set_ylabel('Number of Tracks')
axs[2].tick_params(axis='x')

plt.tight_layout()
plt.show()
```

    C:\Users\PC1\AppData\Local\Temp\ipykernel_5580\2127515794.py:10: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x=released_year_counts.index, y=released_year_counts.values, palette='viridis', ax=axs[0])
    C:\Users\PC1\AppData\Local\Temp\ipykernel_5580\2127515794.py:17: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x=released_month_counts.index, y=released_month_counts.values, palette='Spectral', ax=axs[1])
    C:\Users\PC1\AppData\Local\Temp\ipykernel_5580\2127515794.py:24: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x=released_day_counts.index, y=released_day_counts.values, palette='RdYlBu', ax=axs[2])
    


    
![png](output_20_1.png)
    


### Genre and Music Characteristics
#### Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?


```python
correlation_matrix = df[['streams', 'bpm', 'danceability_%', 'energy_%']].corr()
print(correlation_matrix) # This should suffice, but generating a heatmap makes it easier to visualize.

# Heatmap for correlations
plt.figure(figsize=(8, 6))
sns.heatmap(correlation_matrix, cmap='coolwarm', fmt='.2f', annot=True, square=True, cbar_kws={"shrink": .8})
plt.title('Correlation Between Streams and Musical Attributes')
plt.show()
```

                     streams       bpm  danceability_%  energy_%
    streams         1.000000 -0.002438       -0.105457 -0.026051
    bpm            -0.002438  1.000000       -0.147095  0.025794
    danceability_% -0.105457 -0.147095        1.000000  0.198095
    energy_%       -0.026051  0.025794        0.198095  1.000000
    


    
![png](output_22_1.png)
    


#### Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?


```python
plt.figure(figsize=(8, 6))
sns.heatmap(df[['valence_%','acousticness_%']].corr(), cmap='coolwarm', fmt='.2f', annot=True, square=True, cbar_kws={"shrink": .8})
plt.title('Correlation Between Streams and Musical Attributes')
plt.show()
```


    
![png](output_24_0.png)
    


### Platform Popularity
#### How do the numbers of tracks in spotify_playlists, deezer_playlist, and apple_playlists compare? Which platform seems to favor the most popular tracks?


```python
# Sum the number of tracks for each platform
tracks_summary = {
    'Platform': ['Spotify Playlists', 'Deezer Playlists', 'Apple Playlists'],
    'Number of Tracks': [
        df['in_spotify_playlists'].sum(),
        df['in_deezer_playlists'].sum(),
        df['in_apple_playlists'].sum()
    ]
}

tracks_summary_df = pd.DataFrame(tracks_summary)
display(tracks_summary_df) # This should suffice, but plot for visualization

# Create a pie chart to visualize which platform is favored
plt.figure(figsize=(8, 8)) 
plt.pie(tracks_summary_df['Number of Tracks'], labels=tracks_summary_df['Platform'], autopct='%1.1f%%', startangle=180)
plt.title('Distribution of Tracks Across Platforms', fontsize=12)
plt.axis('equal')  # Equal aspect ratio ensures pie chart is a circle.
plt.show()
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Platform</th>
      <th>Number of Tracks</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Spotify Playlists</td>
      <td>4955719</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Deezer Playlists</td>
      <td>367084</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Apple Playlists</td>
      <td>64625</td>
    </tr>
  </tbody>
</table>
</div>



    
![png](output_26_1.png)
    


### Advanced Analysis
#### Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?


```python
# Group by key and mode, and calculate mean and median streams
grouped = df.groupby(['key', 'mode'])['streams'].agg(['mean', 'median', 'count']).reset_index()
display(grouped)

# Bar Plot for Mean Streams by Key and Mode
plt.figure(figsize=(10, 5))
sns.barplot(data=grouped, x='key', y='mean', hue='mode', palette='coolwarm')
plt.title('Mean of Streams by Key and Mode')
plt.xlabel('Musical Key')
plt.ylabel('Mean of Number of Streams')
# Removed legend as per request
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

# Box Plot to visualize the distribution of streams by Mode
plt.figure(figsize=(10, 5))
sns.boxplot(data=df, x='mode', y='streams', palette='coolwarm')
plt.title('Distribution of Streams by Mode (Major/Minor)')
plt.xlabel('Mode (Major/Minor)')
plt.ylabel('Number of Streams')
plt.tight_layout()
plt.show()
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>key</th>
      <th>mode</th>
      <th>mean</th>
      <th>median</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>Major</td>
      <td>4.019603e+08</td>
      <td>247737946.0</td>
      <td>41</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A</td>
      <td>Minor</td>
      <td>4.173906e+08</td>
      <td>232896922.0</td>
      <td>33</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A#</td>
      <td>Major</td>
      <td>6.275336e+08</td>
      <td>488386797.0</td>
      <td>27</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A#</td>
      <td>Minor</td>
      <td>4.849231e+08</td>
      <td>206929807.0</td>
      <td>30</td>
    </tr>
    <tr>
      <th>4</th>
      <td>B</td>
      <td>Major</td>
      <td>4.363336e+08</td>
      <td>236857112.0</td>
      <td>35</td>
    </tr>
    <tr>
      <th>5</th>
      <td>B</td>
      <td>Minor</td>
      <td>5.825110e+08</td>
      <td>422362992.5</td>
      <td>46</td>
    </tr>
    <tr>
      <th>6</th>
      <td>C#</td>
      <td>Major</td>
      <td>6.285883e+08</td>
      <td>302006641.0</td>
      <td>73</td>
    </tr>
    <tr>
      <th>7</th>
      <td>C#</td>
      <td>Minor</td>
      <td>5.665252e+08</td>
      <td>312622938.0</td>
      <td>47</td>
    </tr>
    <tr>
      <th>8</th>
      <td>D</td>
      <td>Major</td>
      <td>5.720180e+08</td>
      <td>331163090.0</td>
      <td>66</td>
    </tr>
    <tr>
      <th>9</th>
      <td>D</td>
      <td>Minor</td>
      <td>3.425588e+08</td>
      <td>246376690.0</td>
      <td>15</td>
    </tr>
    <tr>
      <th>10</th>
      <td>D#</td>
      <td>Major</td>
      <td>6.819623e+08</td>
      <td>398136734.5</td>
      <td>12</td>
    </tr>
    <tr>
      <th>11</th>
      <td>D#</td>
      <td>Minor</td>
      <td>4.793647e+08</td>
      <td>198275403.0</td>
      <td>21</td>
    </tr>
    <tr>
      <th>12</th>
      <td>E</td>
      <td>Major</td>
      <td>7.605963e+08</td>
      <td>635412045.0</td>
      <td>17</td>
    </tr>
    <tr>
      <th>13</th>
      <td>E</td>
      <td>Minor</td>
      <td>5.083264e+08</td>
      <td>253650850.0</td>
      <td>45</td>
    </tr>
    <tr>
      <th>14</th>
      <td>F</td>
      <td>Major</td>
      <td>5.279311e+08</td>
      <td>286371308.0</td>
      <td>44</td>
    </tr>
    <tr>
      <th>15</th>
      <td>F</td>
      <td>Minor</td>
      <td>4.102836e+08</td>
      <td>248088961.0</td>
      <td>45</td>
    </tr>
    <tr>
      <th>16</th>
      <td>F#</td>
      <td>Major</td>
      <td>4.175450e+08</td>
      <td>235505538.0</td>
      <td>30</td>
    </tr>
    <tr>
      <th>17</th>
      <td>F#</td>
      <td>Minor</td>
      <td>5.954921e+08</td>
      <td>319566866.0</td>
      <td>43</td>
    </tr>
    <tr>
      <th>18</th>
      <td>G</td>
      <td>Major</td>
      <td>4.929813e+08</td>
      <td>266298719.5</td>
      <td>66</td>
    </tr>
    <tr>
      <th>19</th>
      <td>G</td>
      <td>Minor</td>
      <td>3.637593e+08</td>
      <td>250641672.0</td>
      <td>30</td>
    </tr>
    <tr>
      <th>20</th>
      <td>G#</td>
      <td>Major</td>
      <td>5.458044e+08</td>
      <td>330881149.0</td>
      <td>63</td>
    </tr>
    <tr>
      <th>21</th>
      <td>G#</td>
      <td>Minor</td>
      <td>3.219036e+08</td>
      <td>213656754.0</td>
      <td>28</td>
    </tr>
  </tbody>
</table>
</div>



    
![png](output_28_1.png)
    


    C:\Users\PC1\AppData\Local\Temp\ipykernel_5580\1173311263.py:18: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.boxplot(data=df, x='mode', y='streams', palette='coolwarm')
    


    
![png](output_28_3.png)
    


#### Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.


```python
# Step 1: Aggregate Data for Artists Separately for Playlists and Charts
artist_summary = df.groupby('artist(s)_name').agg({
    'in_spotify_playlists': 'sum',
    'in_apple_playlists': 'sum',
    'in_deezer_playlists': 'sum',
    'in_spotify_charts': 'sum',
    'in_deezer_charts': 'sum',
    'in_shazam_charts': 'sum',
    'in_apple_charts': 'sum'
}).reset_index()

# Separate Total Columns for Playlists and Charts
artist_summary['Total_Playlists'] = (
    artist_summary['in_spotify_playlists'] +
    artist_summary['in_apple_playlists'] +
    artist_summary['in_deezer_playlists']
)

artist_summary['Total_Charts'] = (
    artist_summary['in_spotify_charts'] +
    artist_summary['in_deezer_charts'] +
    artist_summary['in_shazam_charts'] +
    artist_summary['in_apple_charts']
)

# Step 2: Filter for Top 10 Artists by Combined Total
artist_summary['Total'] = artist_summary['Total_Playlists'] + artist_summary['Total_Charts']
top_artists = artist_summary.sort_values(by='Total', ascending=False).head(10)

# Step 3: Reshape the Data for Grouped Bar Plot
top_artists_melted = pd.melt(top_artists, 
                             id_vars=['artist(s)_name'], 
                             value_vars=['Total_Playlists', 'Total_Charts'], 
                             var_name='Category', 
                             value_name='Appearances')

# Step 4: Create the Grouped Bar Chart
plt.figure(figsize=(8, 4))
sns.barplot(x='Appearances', y='artist(s)_name', hue='Category', data=top_artists_melted, palette='inferno')
plt.title('Top 10 Most Frequently Appearing Artists in Playlists vs. Charts')
plt.xlabel('Total Appearances')
plt.ylabel('Artist Name')
plt.legend(title='Category', loc='best')
plt.tight_layout()
plt.show()

```


    
![png](output_30_0.png)
    



```python

```

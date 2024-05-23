# **Spotify data 2023 EDA**

As a music🎵 enthusiast, I was interested in exploring this **[Spotify dataset](https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023)** to uncover interesting insights and correlations. I will perform the following analyses, and you can check them out in this **[Kaggle notebook](https://www.kaggle.com/code/wilfridawere/spotify-data-2023-eda)**

* **Number of Tracks released each year**

* **Artist Analysis**:
1. Analyze the number of tracks each artist features in. Pick the top 20 artists. 
1. Examine if the audio features `bpm`, `danceability_%`, `valence_%`, `energy_%`, `acousticness_%`, `liveness_%`, `speechiness_%`,`key`,`mode` tend to co-occur together in the 20 most streamed tracks.
1. Categorical Features: 
   * analyse the Distribution of `key_mode`s
   * examine how `key` and `mode` trend over the years.

# Data Cleaning

The dataset has **953 rows and 24 columns**.

I will make a copy of the original dataset and name it *music.cleaned*

There are **Missing values** in the `in_shazam_charts` and `key` columns. I will drop the `in_shazam_charts` column. Don't need it. The `key` column has **95** missing values.

I used  [Songbpm](https://songbpm.com/) to determine the key and mode for each track. The values are saved in this [CSV file](./Spotify%20Missing%20Keys%20(1).xlsx) and then imputed in order

# Number of Tracks released each year

Most people listen to songs regardless of the year of release. You'll see that in this 2023 dataset.

Number of Tracks released in 2023: 175

Number of Tracks released in 2022: 402

Number of Tracks released in 2021: 119

Number of Tracks released in 2020: 37

Number of Tracks released in 2019: 36

Number of Tracks released in 2018: 10

Number of Tracks released before 2018: 174

# Artist Analysis

## Top 20 Artists with the most Tracks

| Artist(s)_name                                | Number of Tracks |
|--------------------------------------------------|-----------------|
| Taylor Swift                                     | 34                |
| The Weeknd                                       | 22                |
| Bad Bunny                                        | 19                |
| SZA                                               | 19                |
| Harry Styles                                      | 17                |
| Kendrick Lamar                                   | 12                |
| Morgan Wallen                                    | 11                |
| Ed Sheeran                                        | 9                 |
| BTS                                              | 8                 |
| Feid                                              | 8                 |
| Drake, 21 Savage                                  | 8                 |
| Labrinth                                          | 7                 |
| Olivia Rodrigo                                    | 7                 |
| NewJeans                                          | 6                 |
| Doja Cat                                          | 6                 |
| Billie Eilish                                    | 5                 |
| Drake                                              | 4                 |
| IVE                                               | 4                 |
| Arctic Monkeys                                    | 4                 |
| Karol G                                           | 4                 |

# Barplot of the Top 20 artists with most tracks

![Alt text](./Barplot%20of%20Top%2020%20artists%20with%20most%20tracks.png)

# Impute vs Drop

I will impute the missing keys instead of dropping the 95 rows because dropping them will affect the ranking of other artists in the top 20 list. Taylor Swift would still be the top either way.

# Top 20 Most Streamed Tracks

![Alt text](./Correlation%20matrix%20of%20top%2020%20most%20popular%20tracks.png)

1. Energy and Danceability (0.60 correlation):

A correlation of 0.60 indicates a positive and moderately strong relationship.
Energetic music often makes you want to move your body and dance.

2. Energy and Valence (0.53 correlation):

The correlation of 0.53 is again positive but slightly weaker than the energy-danceability correlation.
Energetic music can often be uplifting, exciting, or motivating.

# Distribution of Key_Modes
​
During Data Cleaning, I added another column `key_mode`to combine the `key` and `mode `columns.

| Keys used | Count |
|---|---|
| C# Major  | 73    |
| C Major   | 73    |
| G Major   | 66    |
| D Major   | 66    |
| G# Major  | 63    |
| C# Minor  | 47    |
| B Minor   | 46    |
| F Minor   | 45    |
| E Minor   | 45    |
| F Major   | 44    |
| A Major   | 43    |
| F# Minor  | 43    |
| B Major   | 35    |
| A Minor   | 33    |
| F# Major  | 30    |
| G Minor   | 30    |
| A# Minor  | 30    |
| G# Minor  | 29    |
| A# Major  | 27    |
| D# Minor  | 21    |
| C Minor   | 19    |
| E Major   | 18    |
| D Minor   | 15    |
| D# Major  | 12    |

![Alt text](./Trends%20of%20Key_modes%20over%20time.png)

When listening to music one day with my sister she said that many songs these days sound **'sad'**. I studied music in highschool so I knew she meant that more songs are in the **Minor mode**. The figure above shows that trend.

Feel free to do more analyses using this spotify dataset. Contact me for any changes and feedback

***Explore and be teachable***

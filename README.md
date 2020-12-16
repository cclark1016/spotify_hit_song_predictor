# spotify_hit_song_predictor

## Topic
I am researching the characteristics of songs that make them likely to become top hits and whether those characteristics change over time. This information is important for both labels and artists as they fund and work through the creative song writing process.  

## Data Source
I am using Spotify song data to train the ML model. The list of 175K+ songs being analyzed was pulled from a Kaggle dataset (https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks) built using Spotify APIs. To identify songs that are classified as hits I have grouped songs from the Billboard Top 100 Year End lists beginning in 1948 into a single Spotify playlist and exported that playlist into a Postgres DB. 
### Song Characteristics Imported
Numerical:
- acousticness (Ranges from 0 to 1)
- danceability (Ranges from 0 to 1)
- energy (Ranges from 0 to 1)
- duration_ms (Integer typically ranging from 200k to 300k)
- instrumentalness (Ranges from 0 to 1)
- valence (Ranges from 0 to 1)
- popularity (Ranges from 0 to 100)
- tempo (Float typically ranging from 50 to 150)
- liveness (Ranges from 0 to 1)
- loudness (Float typically ranging from -60 to 0)
- speechiness (Ranges from 0 to 1)
- year (Ranges from 1921 to 2020)

Dummy:
- mode (0 = Minor, 1 = Major)
- explicit (0 = No explicit content, 1 = Explicit content)

Categorical:
- key (All keys on octave encoded as values ranging from 0 to 11, starting on C as 0, C# as 1 and so on…)
- artists (List of artists mentioned)
- release_date (Date of release mostly in yyyy-mm-dd format, however precision of date may vary)
- name (Name of the song)

## Questions to answer
- Can a hit song be predicted with 80%+ accuracy based solely on song characteristics?
- Do the characteristics of hit songs change based on the year they were released? 
- Can top 100 songs from publications besides the Billboard be predicted with 80% accuracy based solely on song characteristics? How do the characteristics of top songs according to these publications vary?
- What combination of characteristics makes a song most likely to be a hit? 

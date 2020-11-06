# eargasmAI
**your Spotify library analysis, visualization and automatic playlist recommendation system**

*by Adam Siemaszkiewicz*


# Summary

The idea behind this repo is to use the a dataset of tracks published to my music blog [eargasm music](https://open.spotify.com/user/eargasmusic?si=fnwCvcPhTNeBUMDxP4mx1A). There are over 3600 tracks in the database collected throughout the years and assigned to almost 30 different playlists. I divided my work into three main categories:
1. [Data Retrieval](#data-retrieval) - Fetch the tracks information using Spotify Web API, organize it and export for later use.
2. [Data Exploration](#data-exploration) - Explore the basic as well as analytical audio features of the tracks and visualize them.
3. [Playlist Classification](#playlist-classification) - Create a machine learning classification model to assign new tracks to existing playlists.

![eargasm music](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/files/eargasm-header.png)

# Data Retrieval

[eargasm_DataRetrieval.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_DataRetrieval.ipynb)

This notebook uses [Spotipy](https://spotipy.readthedocs.io/) Python library to access [Spotify Web API](https://developer.spotify.com/documentation/web-api/) and fetch the playlist information from the blog using `spotipy.user_playlists()` module. Once I have a list of all playlists I can start fetching track info:
- Basic track information using `spotipy.playlist_items()` such as: artist, name, duration, url etc.
- Audio features using `spotipy.audio_features()` such as danceability, acousticness, valence etc.
- Audio analysis using `spotipy.audio_analysis()` such as tempo, key, mode etc.
- Genres using `spotipy.artist()` to get a list of genres assigned for each artist
All the data was organized using [Numpy](https://numpy.org/) and [Pandas](https://pandas.pydata.org/) libraries and exported to CSV files for later use.

# Data Exploration

[eargasm_DataExploration.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_DataExploration.ipynb)

This notebook imports track data fetched previously using [DataRetrieval.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_DataRetrieval.ipynb) and uses various Python libraries to analyse and visualize the data such as:
- most popular artists and genres using [WordCloud](https://github.com/amueller/word_cloud) and [Plotly](https://plotly.com/)
- interactive box plots showing statistical representation of the track features for each playlist using [Plotly](https://plotly.com/)
- heatmap showing correlation between the audio features using [Plotly](https://plotly.com/)
- interactive density and distribution plots aggregated by selected features using [Plotly](https://plotly.com/)
- interactive playlist comparison using radar and scatter plots using [Plotly](https://plotly.com/)

# Playlist Classification

[eargasm_Classification.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_PlaylistClassification.ipynb)

This notebook import track data fetched previously using [DataRetrieval.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_DataRetrieval.ipynb) and uses it to build a machine learning model meant to assign new tracks to existing playlists according to the following steps:
- feature engineering
- selecting a number of best-performing classifiers for further development using cross-validation
- evaluating selected estimators by hyperparameter tuning, confusion matrix and learning curves visualization
- choosing and evaluating the real life performance of the model

# Thank you!


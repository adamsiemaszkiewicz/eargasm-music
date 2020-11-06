# eargasm music
**by Adam Siemaszkiewicz**

# Summary

The idea behind this repo is to use the a dataset of tracks published to my music blog [eargasm music](https://open.spotify.com/user/eargasmusic?si=fnwCvcPhTNeBUMDxP4mx1A). There are over 3600 tracks in the database collected throughout the years and assigned to almost 30 different playlists. I divided my work into three main categories:
1. [Data Retrieval](#data-retrieval) - Fetch the tracks information using Spotify Web API, organize it and export for later use.
2. [Data Exploration](#data-exploration) - Explore the basic as well as analytical audio features of the tracks and visualize them.
3. [Playlist Classification](#playlist-classification) - Create a machine learning classification model to assign new tracks to existing playlists.

# Data Retrieval

[eargasm_DataRetrieval.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_DataRetrieval.ipynb)

This notebook uses [Spotipy](https://spotipy.readthedocs.io/) Python library to access [Spotify Web API](https://developer.spotify.com/documentation/web-api/) and fetch the playlist information from the blog using `spotipy.user_playlists()` module. Once I have a list of all playlists I can start fetching track info:
- Basic track information using `spotipy.playlist_items()` such as: artist, name, duration, url etc.
- Audio features using `spotipy.audio_features()` such as danceability, acousticness, valence etc.
- Audio analysis using `spotipy.audio_analysis()` such as tempo, key, mode etc.
- Genres using `spotipy.artist()` to get a list of genres assigned for each artist
All the data was organized used Pandas and exported to CSV files.

# Data Exploration

[eargasm_DataExploration.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_DataExploration.ipynb)

# Playlist Classification

[eargasm_Classification.ipynb](https://github.com/adamsiemaszkiewicz/eargasm-music/blob/main/eargasm_PlaylistClassification.ipynb)

# Thank you!


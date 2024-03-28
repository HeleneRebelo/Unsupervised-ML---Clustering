# Unsupervised ML: Clustering Songs

## Context

Moosic is an innovative start-up that creates playlists curated by music experts, always considering old music, but with an eye on new trends. Users can listen to these playlists on their favorite streaming services (e.g. Spotify, Apple Music, and YouTube Music) by simply signing up on their website. However, the company is growing fast, and it has become challenging for music experts to quickly create playlists to keep up with the market.

## Main Objective

Moosic provides playlist creation automation to help music experts by building a prototype for grouping songs into playlists using KMeans.

## Challenge

Categorize the songs into an appropriate number of clusters. Is K-Means an effective method for creating playlists or should we explore other algorithms or methods in our playlist creation process?

## Folder Structure

/docs: This directory contains the final presentation for the project.

/src: Inside this folder, you will find the Notebook with the codes.

## Data Source, Cleaning and Preparation

The dataset consisted of 5,235 song titles with Spotify audio features that describe them. After cleaning the data, using only numeric values, and eliminating duplicates, the total was reduced to 5,114 songs. 

### Dataset

This dataset includes various audio features, among them, some are classical musical attributes such as pitch, mode, and tempo. In addition, exclusive analyses prepared by the Data Science and Sound Engineering team are present, such as danceability, energy, and valence.

Therefore, the dataset has the following audio features:

- acousticness: A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.

- danceability: describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is the least danceable and 1.0 is most danceable.

- duration_ms: The duration of the track in milliseconds.
	
- energy: is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy.

- instrumentalness: Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly “vocal”. The closer the instrumentalness value is to 1.0, the greater the likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0.	

- key: The key the track is in. Integers map to pitches using standard Pitch Class notation. E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on.	

- liveness: Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides a strong likelihood that the track is live.	

- loudness: The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing the relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typically range between -60 and 0 db.	

- mode: indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.	

- speechiness: detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.	

- tempo: The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.	

- time_signature: An estimated overall time signature of a track. The time signature (meter) is a notational convention to specify how many beats are in each bar (or measure).	

- valence: A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).
  
## Methodology

The subsequent step involves selecting a Scaler. MinMaxScaler() is employed for data normalization, however, RobustScaler() demonstrated comparable results. 
We use Principal Component Analysis - PCA to determine the combination of the most relevant features with a cumulative variance of 0.95. 
To determine the ideal number of clusters, we used the Elbow and Silhouette methods, which indicated that around 20 clusters would be ideal.
Additionally, obtaining an API key from Spotify would enable the development of an application that can directly organize clusters within your Spotify account.

## Analysis Summary

- The k-Means clustering algorithm demonstrated its effectiveness in segmenting our dataset into distinct, meaningful groups.

- The optimal number of clusters for this particular dataset seems to be around 20, as it provides the highest silhouette score, indicating a better structure and separation between the clusters.

- Using a machine to create a playlist is time and cost-effective, even if the results are not as accurate as those from music experts.

### This project was made possible by the collaborative efforts of our team:
Me, [TsveteLina Yordanova](https://github.com/LinaYorda), and Gustavo Rodríguez





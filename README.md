# Hip-hop Instrumental Classifier

## Purpose: To better understand the music I produce, the music I listen to, and their relationship to one another.

#### Technologies Used: Tableau (exploratory data analysis/visualization), Data Science Toolkit (Pandas, Scikit-learn, Matplotlib, etc.), Keras (Artificial N.N.)


### Data Collection:

Using Spotify's API and their Spotipy library, I gathered the audio features of all songs of my top 50 most impactful and streamed artists into a pandas dataset. The data was exported, cleaned, and reformatted seperately for the data analysis.


### EDA:

The goal was to not only explore relationships between audio features of my favorite songs, but also recognize similarities/differences between the audio feature data of my beats and my favorite songs.

#### [Tableau Presentation](https://public.tableau.com/views/MyMusicandMyFavoriteArtistsMusic/JointAnalysisofMyMusicandMyFavoriteArtistsMusic?:language=en-US&:display_count=n&:origin=viz_share_link)

In this short presentation, I chose to focus on four main aspects of the data:
1. Am I more likely to listen to artists based on how much their music leverages the minor scale?
   - How: Using a scatterplot and regression line to explore the association between an artist's rank and percentage of their discography in minor.
2. Are there any relationships between audio features in my favorite music?
   - How: Created correlation heatmap to quickly identify any relationships.
3. Are there any relationships between audio features in my music?
   - How: Same as above.
4. Are there any similarities in audio feature relationships between my beats and my favorite songs?
   - How: Visually compared the two heatmaps I created.



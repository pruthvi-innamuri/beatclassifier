# Hip-hop Instrumental Classifier

### Purpose
1. To better understand the music I produce, the music I listen to, and their relationship to one another.
2. Build a functioning A.N.N. classifier that categorizes my self-produced instrumentals into related/relevant artist.





## Data Collection:

#### Technologies Used: Spotipy, Python Data Science Toolkit

1. I created a Spotify client to communicate with their Web API and fetch data. 
<img src="https://user-images.githubusercontent.com/56245127/149641053-cc8a3dc8-f086-439b-9fba-b3d44129ba44.jpg"  width="300" />

2. I set up a Jupyter Notebook and created a spotipy.Spotify instance, through which I could explore the entire API. 
<img src="https://user-images.githubusercontent.com/56245127/149641188-19d11c3e-e833-4ab0-bc0f-ce2e71d5e486.jpg"  width="300" />

3. I determined my top artists (streamed) using https://www.statsforspotify.com/. I edited this list to include artists I thought were influential to my production style.
<img src="https://user-images.githubusercontent.com/56245127/149644928-03b0c7b6-ddab-4515-9d1c-496f23bb3019.jpg"  width="300" />

4. I gathered all song data into a Pandas dataframe (refer to Jupyter Notebook) and exported it to csv (for future usage).




## EDA:

#### Technologies Used: Tableau, Excel

The goal was to not only explore relationships between audio features of my favorite songs, but also recognize similarities/differences between the audio feature data of my beats and my favorite songs.

<img src="https://user-images.githubusercontent.com/56245127/149640850-56ea000f-2622-4e76-8d2f-d4db83958712.jpg"  width="200" height="200" />




#### [Presentation](https://public.tableau.com/views/MyMusicandMyFavoriteArtistsMusic/JointAnalysisofMyMusicandMyFavoriteArtistsMusic?:language=en-US&:display_count=n&:origin=viz_share_link)

In this short presentation, I chose to focus on four main aspects of the data:
1. Am I more likely to listen to artists based on how much their music leverages the minor scale?
   - How: Using a scatterplot and regression line to explore the association between an artist's rank and percentage of their discography in minor.
2. Are there any relationships between audio features in my favorite music?
   - How: Created correlation heatmap to quickly identify any relationships.
3. Are there any relationships between audio features in my music?
   - How: Same as above.
4. Are there any similarities in audio feature relationships between my beats and my favorite songs?
   - How: Visually compared the two heatmaps I created.




## Building a Multiclass Classification Artificial Neural Network

#### Technologies Used: Keras/Tensorflow, Scikit-learn, Python Data Science Toolkit 



# Hip-hop Instrumental Classifier


#### [My Spotify](https://open.spotify.com/artist/4gtbYuWL3jPmNndg8H6bsW?si=MaBUis3eQQSoi6s9KlQQew)


## Background

A new wave in music, shaping how hip-hop artists find instrumentals is "Type Beats". "Type Beats" refer to instrumentals that fit a specific 
well-known artist's sound. For example, a quick search on Youtube for "Drake Type Beat" will yield thousands of results of instrumentals similar to Drake's sound. This classification of beats into a specific artist(s) is particularly effective for producers to convey the musical character of their tracks' since listeners know the artist as well. I wanted to see if I could use machine learning to classify my beats for me!


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

I followed a two step process in building this classifier:
1. Build a simple binary classifier to familiarize myself with Keras tools and the data
2. Scale the binary classifier architecture to handle multiclass classification

### Binary Classifier (Classifying songs as closer to Drake's music or NAV's)

I referred to online forums and articles for an example A.N.N. architecture to build off of. Through hours of testing and tinkering with hyperparameters, 
I learned their unique effects on a model's loss and accuracy. Firstly, I added an extra layer to my A.N.N. to capture the depth of relationships within the data.
Secondly, I increased the number of nodes as well since I noticed my training loss decreasing till the very end. Lastly, I added dropout between the first and second
hidden layers to prevent overfitting. Dropout helped increase the overall accuracy. 

My biggest takeaway from building this classifier was to always __scale input variables__. This increased my overall train/test accuracy by 20%.


#### [Jupyter Notebook](https://github.com/pruthvi-innamuri/beatclassifier/blob/59c9182f9156a1d772617a8e88a80ab135b3f346/preprocessingandbinarymodel.ipynb)

#### [Binary Model - 92% Accuracy](https://github.com/pruthvi-innamuri/beatclassifier/blob/ea86bd16f9a7242de275b91d2aca6d38c0f908ed/binaryclassificationninetyfour.h5)



### Full Classifier

Using the same A.N.N. as before, but with categorical crossentropy loss function, I trained and tested my classifier on the data. I was reach hardly 10% accuracy. Instead of brute force guessing the ideal hyperparameters myself, I used Sklearn's GridSearch functionality. GridSearch allows me to provide a function that builds an A.N.N. and provide a variety of different hyperparameters (like batch_size, # of nodes, # of layers, activation function, etc.) and it will determine the optimal combination of hyperparameters. I guessed a large number of nodes and layers to capture the data's complexity. 

Since this function requires extra processing power and takes a while, I sped up the process by running it in Google Colab with a GPU hardware accelerator.


#### [Google Colab](https://colab.research.google.com/drive/1rdsstVpDfWT5Tvjhs2BIBQdhfURWkJLp?usp=sharing)





BACKGROUND

-Music is an integral part of our daily lives 
-50 Billion dollar industry 
-There are many stakeholders who would want to predict song popularity. 
Examples: 
           • Venues 
           • Music distributors 
           
HYPOTHESIS AND DESIRED OUTCOMES

Problem Statement: To identify the popularity of a given song
We chose this problem to understand the features that are important in predicting the popularity of a song
This can help an artist to understand if their song is going to be popular or not 

• Using song features, build a model which can predict if a given song will be above or below the mean of song popularity scores of the data (0.487166) 

• We chose 6 classification algorithms in order to compare the results and see which one gives us optimal results.

ABOUT DATA
Million Song Dataset (MSD) is freely available collection of audio features and metadata for a million contemporary tracks 

From The Echo Nest (now owned by Spotify) 

Size of dataset - 300GB

One Million Songs 

54 features and 1M records

DATA PREPROCESSING

Downloaded the entire dataset on AWS EC2 node 

Extracted all the metadata using Python and created a CSV summary file 

Each song has 53 features such as Mode, Tempo, Duration, Title,    End of Fade In etc.,

Traditional data cleansing 

Removed records that are missing year or song popularity metric 

Removed Variables with zero variance, zero cardinality and high cardinality 

Removed columns which had more than 50% missing data

Removed columns which were not significant for our analysis


DATA EXPLORATION
After data cleansing, left with 306297 rows 

Correlation matrix: 

We can see a high correlation between
duration and  start_of_fade_out
artist_familiarity and artist_hotness
song_hotness with artist_familiarity and artist_hotness


FEATURE Importance and Top Features 

Extra Trees Classifier to determine feature importance score  
We have removed variables which are not significant to our analysis :
Mode, time_signature, key

By removing these variables we were able to achieve high performance because their p-value is high and does not contribute significantly to our model

We have verified these features using RFE (Recursive Feature Elimination)


MODEL EVALUATION

Logistic Regression gives the best accuracy of all the models tried
 
It also had the best Cross validation Score and  Accuracy (0.69 and 0.69)

Parameters for model building

For Random forest: 100 decision trees

We tried altering the parameters like max_depth, n_estimators to maximize accuracy
We have achieved an area under curve of 70%
We have also validated the model by checking the evaluation metrics for different thresholds 


CONCLUSIONS, FUTURE AND Spin - OFFS

• Predicted song popularity based on song features 

• Artist familiarity, Artist Hotness, Loudness, Tempo, End of Fade In are top five features 

• Logistic Regression gave the best results 

• Future 

• Include song genres, most frequent words in lyrics as features 

• Spin-off Projects 

• Use similar tracks and similar artists information to create inter-relationship map for artists and songs 




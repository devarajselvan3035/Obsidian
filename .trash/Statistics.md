Statistical Modelling using Python | Aman Kharwal
Statistical modelling is a form of mathematical modelling that involves statistics to estimate or predict real-world behaviours, trends, and future outcomes based on data. It involves the construction of a statistical model, which is a formal representation of relationships between variables, typically expressed in the form of mathematical equations. So, if you want to learn how to perform statistical modelling, this article is for you. In this article, I’ll take you through the task of statistical modelling using Python.

What is Statistical Modelling? And How It’s Different From Machine Learning Model Training?
Statistical modelling is a mathematical framework used to describe the relationships between variables in the form of equations, usually involving stochastic elements (randomness). It is primarily focused on inference, which means understanding the relationships between variables and quantifying how certain factors influence outcomes.

Statistical models are built based on assumptions about the data distributions and the nature of the relationships between variables. Common examples include linear regression, logistic regression, and analysis of variance (ANOVA).

The difference between statistical modelling and machine learning model training is that statistical modelling is primarily concerned with inference. It seeks to understand the underlying relationships between variables and to quantify how predictors influence the response variable. It often tests hypotheses about these relationships.

Whereas Machine Learning model training focuses on prediction. The primary goal is to create models that can make accurate predictions on new, unseen data. Machine learning often cares less about the ‘why’ of the data relationships and more about the ‘how well’ it can predict the outcome.

To explain the use of statistical modelling, I’ll take you through the task of statistical modelling of music features, where we will aim to identify what music features determine the popularity of music tracks. You can download the dataset to work on this problem from here.

Now, let’s get started with the task of statistical modelling of music features by importing the dataset and the necessary Python libraries:

1
import pandas as pd
5
print(music_data.head())
   Unnamed: 0                                   Track Name  \
0           0                                Bijlee Bijlee   
1           1                                  Expert Jatt   
2           2  Kaun Nachdi (From "Sonu Ke Titu Ki Sweety")   
3           3                                  Na Na Na Na   
4           4                                  Patiala Peg   

                      Artists                         Album Name  \
0               Harrdy Sandhu                      Bijlee Bijlee   
1                       Nawab                        Expert Jatt   
2  Guru Randhawa, Neeti Mohan   High Rated Gabru - Guru Randhawa   
3                      J Star                        Na Na Na Na   
4              Diljit Dosanjh  Do Gabru - Diljit Dosanjh & Akhil   

                 Album ID                Track ID  Popularity Release Date  \
0  3tG0IGB24sRhGFLs5F1Km8  1iZLpuGMr4tn1F5bZu32Kb          70   2021-10-30   
1  2gibg5SCTep0wsIMefGzkd  7rr6n1NFIcQXCsi43P0YNl          65   2018-01-18   
2  6EDbwGsQNQRLf73c7QwZ2f  3s7m0jmCXGcM8tmlvjCvAa          64   2019-03-02   
3  4xBqgoiRSOMU1VlKuntVQW  5GjxbFTZAMhrVfVrNrrwrG          52         2015   
4  1uxDllRe9CPhdr8rhz2QCZ  6TikcWOLRsPq66GBx2jk67          46   2018-07-10   

   Duration (ms)  Explicit  ... Energy  Key  Loudness  Mode  Speechiness  \
0         168450     False  ...  0.670    1    -5.313     0       0.1430   
1         199535     False  ...  0.948    6    -2.816     0       0.1990   
2         183373     False  ...  0.830    4    -3.981     0       0.0455   
3         209730     False  ...  0.863    3    -3.760     1       0.0413   
4         188314     False  ...  0.811    5    -3.253     0       0.1840   

   Acousticness  Instrumentalness  Liveness  Valence    Tempo  
0        0.2690          0.000000    0.0733    0.643  100.004  
1        0.2980          0.000000    0.0784    0.647  172.038  
2        0.0357          0.000000    0.0419    0.753  127.999  
3        0.3760          0.000014    0.0916    0.807   95.000  
4        0.0259          0.000000    0.3110    0.835  175.910  

[5 rows x 22 columns]
Let’s have a look at the column info and summary statistics before moving forward:

1
music_data.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 100 entries, 0 to 99
Data columns (total 22 columns):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 0   Unnamed: 0        100 non-null    int64  
 1   Track Name        94 non-null     object 
 2   Artists           94 non-null     object 
 3   Album Name        94 non-null     object 
 4   Album ID          100 non-null    object 
 5   Track ID          100 non-null    object 
 6   Popularity        100 non-null    int64  
 7   Release Date      100 non-null    object 
 8   Duration (ms)     100 non-null    int64  
 9   Explicit          100 non-null    bool   
 10  External URLs     100 non-null    object 
 11  Danceability      100 non-null    float64
 12  Energy            100 non-null    float64
 13  Key               100 non-null    int64  
 14  Loudness          100 non-null    float64
 15  Mode              100 non-null    int64  
 16  Speechiness       100 non-null    float64
 17  Acousticness      100 non-null    float64
 18  Instrumentalness  100 non-null    float64
 19  Liveness          100 non-null    float64
 20  Valence           100 non-null    float64
 21  Tempo             100 non-null    float64
dtypes: bool(1), float64(9), int64(5), object(7)
memory usage: 16.6+ KB
1
print(music_data.describe())
       Unnamed: 0  Popularity  Duration (ms)  Danceability     Energy  \
count  100.000000  100.000000     100.000000    100.000000  100.00000   
mean    49.500000   50.950000  210543.180000      0.767210    0.79763   
std     29.011492   16.496326   37961.050214      0.085302    0.11572   
min      0.000000    0.000000  141862.000000      0.501000    0.47700   
25%     24.750000   46.000000  186098.500000      0.714750    0.71125   
50%     49.500000   56.500000  205076.000000      0.772000    0.81700   
75%     74.250000   62.000000  226079.000000      0.826500    0.88125   
max     99.000000   72.000000  367818.000000      0.959000    0.98800   

             Key    Loudness       Mode  Speechiness  Acousticness  \
count  100.00000  100.000000  100.00000   100.000000    100.000000   
mean     4.54000   -4.399930    0.43000     0.115615      0.165559   
std      3.64434    1.612703    0.49757     0.075819      0.152536   
min      0.00000   -8.272000    0.00000     0.029400      0.001090   
25%      1.00000   -5.465250    0.00000     0.057700      0.037500   
50%      4.00000   -4.252500    0.00000     0.086150      0.128000   
75%      7.25000   -3.163250    1.00000     0.160000      0.236750   
max     11.00000   -0.223000    1.00000     0.340000      0.620000   

       Instrumentalness    Liveness     Valence       Tempo  
count        100.000000  100.000000  100.000000  100.000000  
mean           0.005236    0.185791    0.659259  119.371470  
std            0.028979    0.170086    0.183901   29.058698  
min            0.000000    0.034600    0.073900   78.991000  
25%            0.000000    0.076900    0.558250   97.042500  
50%            0.000000    0.122000    0.672500  107.984000  
75%            0.000041    0.225250    0.793750  132.259000  
max            0.270000    0.823000    0.940000  189.857000  
I noticed an unnamed column. Before removing it, let’s have a look at whether the data has null values or not:

1
music_data.isnull().sum()
Unnamed: 0          0
Track Name          6
Artists             6
Album Name          6
Album ID            0
Track ID            0
Popularity          0
Release Date        0
Duration (ms)       0
Explicit            0
External URLs       0
Danceability        0
Energy              0
Key                 0
Loudness            0
Mode                0
Speechiness         0
Acousticness        0
Instrumentalness    0
Liveness            0
Valence             0
Tempo               0
dtype: int64
Now let’s perform data cleaning on this data:

1
# dropping the 'Unnamed: 0' column
2
music_data_cleaned = music_data.drop(columns=['Unnamed: 0'])
3

11
plt.show()
Statistical Modelling: Distribution of Popularity Scores
The distribution of popularity scores shows a range mainly between 40 to 70, with peaks around the 50s and 60s. This indicates that most tracks in this dataset have moderate to high popularity.

Now, let’s have a look at the correlation matrix:

1
plt.figure(figsize=(12, 10))
2
correlation_matrix = music_data_cleaned.select_dtypes(include=['float64', 'int64']).corr()
3
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt=".2f")
4
plt.title('Correlation Matrix of Numerical Features')
5
plt.show()
Correlation Matrix of Numerical Features
The heatmap provides insights into how various features are related to each other and the popularity of the tracks. Notably, Popularity seems to have some level of positive correlation with Loudness and Energy, while it has slight negative correlations with Acousticness. This suggests that louder and more energetic tracks tend to be more popular, while more acoustic tracks tend to be less popular.

Danceability and Valence (the musical positiveness conveyed by a track) also show some positive correlation with popularity, indicating that tracks that are more danceable and have a happier tone might be preferred by listeners.

Now, let’s delve into the individual feature impacts on the popularity of music tracks. We’ll focus on several key features based on our initial observations from the correlation matrix. Specifically, we’ll analyze:

Danceability vs. Popularity
Energy vs. Popularity
Loudness vs. Popularity
Acousticness vs. Popularity
Valence vs. Popularity
For each of these features, we’ll create scatter plots to visualize their relationship with popularity. This will help us understand how each feature might influence the popularity of a track:

1
# creating scatter plots for various features vs. popularity
2
features = ['Danceability', 'Energy', 'Loudness', 'Acousticness', 'Valence']
3
plt.figure(figsize=(15, 10))
4

13
plt.show()
statistical modelling: music features vs popularity
Here are the scatter plots visualizing the relationships between various musical features and the popularity of tracks:

Danceability vs. Popularity: Higher danceability scores tend to correlate with moderate to high popularity. This suggests that more danceable tracks are generally more popular.
Energy vs. Popularity: Similar to danceability, higher energy levels in tracks often correlate with higher popularity. This aligns with the trend that energetic tracks are preferred by listeners.
Loudness vs. Popularity: There’s a trend showing that louder tracks tend to have higher popularity scores. This might reflect listener preference for more vibrant and powerful sound profiles.
Acousticness vs. Popularity: Acousticness shows a somewhat inverse relationship with popularity, where tracks with lower acousticness tend to be more popular. This could suggest that highly acoustic tracks are less favoured in the dataset’s music genre context.
Valence vs. Popularity: Tracks with higher valence, which indicates a happier or more positive tone, show a slight tendency towards higher popularity. This might imply that listeners prefer tracks that have a positive emotional tone.
Now, let’s have a look at how danceability, energy, and other features impact popularity differently when the track is explicit versus when it’s not. This can reveal whether explicit content has a modifying effect on the relationship between audio features and popularity:

1
# creating plots for danceability vs. popularity and energy vs. popularity, segmented by explicit content
2
plt.figure(figsize=(14, 7))
3

19
plt.show()
Explicit and non explicit music vs popularity
The segmented scatter plots for Danceability vs. Popularity and Energy vs. Popularity, divided by whether tracks are explicit or not, show some interesting trends:

Danceability vs. Popularity: Both explicit and non-explicit tracks show a positive trend between danceability and popularity. However, explicit tracks tend to cluster slightly higher on the popularity scale at similar levels of danceability compared to non-explicit tracks.
Energy vs. Popularity: Similar to danceability, there’s a generally positive relationship between energy and popularity for both explicit and non-explicit tracks. Explicit tracks appear to achieve higher popularity at lower energy levels compared to non-explicit tracks, suggesting that the explicit content may appeal to certain listener groups more, irrespective of energy level.
Statistical Modelling of Music Features
Now, let’s quantitatively assess the impact of various features on the popularity of music tracks using statistical modelling. We can use a regression model. This will allow us to understand which features are significant predictors of popularity, and quantify their impact.

For statistical modelling, we’ll use features that show promising relationships and convert categorical data (like Explicit) into a format suitable for regression analysis. We’ll also include the Key and Mode as they might carry additional information about the musical properties of the tracks.

Let’s start by preparing the features and setting up our dataset for statistical modelling using Linear Regression:

1
from sklearn.model_selection import train_test_split
2
from sklearn.linear_model import LinearRegression
3
from sklearn.metrics import mean_squared_error, r2_score
4
from sklearn.preprocessing import StandardScaler
5

34
coefficients = pd.Series(model.coef_, index=features)
35
coefficients
Danceability        1.249640e+00
Energy             -3.204815e+00
Loudness            1.141456e+00
Acousticness        2.469403e+00
Valence             2.125671e+00
Explicit            1.620926e-14
Key                -3.189486e+00
Mode               -5.859715e+00
Speechiness         3.398224e-02
Instrumentalness    3.390750e-01
Tempo              -1.865736e+00
dtype: float64
The output above represents the coefficients from the regression model quantifying the impact of various musical features on track popularity. A positive coefficient indicates that an increase in the feature is associated with an increase in popularity, and vice versa for a negative coefficient.

For instance, Danceability (1.249640), Loudness (1.141456), Acousticness (2.469403), and Valence (2.125671) all have positive coefficients, suggesting that tracks with higher values in these features tend to be more popular.

On the contrary, Energy (-3.204815), Key (-3.189486), Mode (-5.859715), and Tempo (-1.865736) are negatively associated with popularity, indicating that higher values in these features could lead to lower popularity.

The coefficients for Explicit (1.620926e-14) and Speechiness (0.03398224) suggest a negligible impact on the popularity, with Explicit essentially having no effect. Instrumentalness (0.3390750) shows a minor positive influence.

Summary
So, Statistical modelling is a mathematical framework used to describe the relationships between variables in the form of equations, usually involving stochastic elements (randomness). It is primarily focused on inference, which means understanding the relationships between variables and quantifying how certain factors influence outcomes.

I hope you liked this article on how to perform Statistical Modelling using Python. Feel free to ask valuable questions in the comments section below. You can follow me on Instagram for many more resources.

Aman Kharwal
Aman Kharwal
Data Strategist at Statso. My aim is to decode data science for the real world in the most simple words.
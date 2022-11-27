# 2022-2 Machine Learning Termproject - Movie Recommendation System
## Abstract
### About Repository
Repository that saved the term project conducted by Machine Learning (Guidance Professor: Professor Won Kim) in Gachon University's software major class in the second semester of 2022

### Input and Output
* Input : Dataset(Dataframe)
* Output : Results for each function (RMSE SCORE, ACCURACY SCORE - Only Content based, Recommended Movie List)

## Explain about Project
### Business Objective
**Goal - Recommend the movie**

In these days, Popularity of the OTT service, interest in movies and TV  dramas has also increased. Therefore, this term project will be conducted to create an algorithm that recommends the genre of the movie based on the ratings of users. Through this, Immediately after the user subscribes to the OTT service, if the user puts in his or her favorite movie (more than three), he or she tries to create a recommendation system that shows the recommended movie to the user.

Since users can receive various inputs, it is predicted that it will be able to develop into a system that recommends top 5 movies to users who are new to OTT platforms such as Netflix and Watcha.
In the case of content-based, it is judged that there is room for use as a movie search system in the future because it is a keyword-centered system.

### Data Exploration
#### Train Dataset
Link : https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset 

movies_metadata.csv(+credits.csv, keywords.csv) + links.csv + ratings.csv (using movie Id attribute)

- movies_metadata.csv : Contains information about movies

- credits.csv : consists character, producer, director information about movie

- keywords.csv : consists key word about movie

- Links.csv : contains the TMDB and IMDB IDs of movie

- Ratings.csv : contains 1048576 rating information

**Number of total data : 104876**

#### Test Dataset
Link : https://ieee-dataport.org/open-access/imdb-users-ratings-dataset

links.csv(in training dataset) + Dataset.npy

**Number of total data : 469820(but any records with IMDB IDs that aren’t in the link.csv file will be dropped)**


## Structure of Giant Function
![Structure](https://user-images.githubusercontent.com/87214724/204139874-c999be89-1913-4470-a8e0-63573ca45b18.png)

### Collaborative Filtering - Matrix Factorization
Matrix => relationship between ‘user_id’ and ‘imdb_id’ (in movies_metadata) and Store the rating score 

* Update: Stochastic Gradient Descent

* Accuracy: RMSE SCORE

### Content based - Cosine Similarity
Measure the RMSE and acuity using the top 5 rating for each user

1. Vectorize the matrix 
2. run pairwise cosine similarity
3. Sort 
4. match the similarities to the ‘movie titles’ and ‘ids’

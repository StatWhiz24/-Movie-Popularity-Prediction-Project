# Movie Popularity Prediction Project

## Project Overview
This project explores the relationship between various attributes of a movie and its popularity, as measured by the audience score. Using a dataset that combines information from Rotten Tomatoes and IMDB, we develop a multiple linear regression model to identify the key predictors of movie popularity. By doing so, we aim to understand which attributes make a movie more likely to resonate with audiences.

## Data Description
The dataset contains 651 randomly sampled movies released before 2016. Each row represents a movie, and each column represents a characteristic of that movie. Although the dataset allows us to generalize to a broader population of films, it's important to note that this study is observational. Due to the voluntary nature of rating and voting on platforms like IMDB and Rotten Tomatoes, potential biases may exist in the data.

## Research Question
Our primary research question is: **Is a movie’s popularity, as measured by audience score, related to its type, genre, runtime, IMDB rating, IMDB number of votes, critics rating, critics score, audience rating, and Oscar awards obtained (for actors, actresses, directors, or best picture)?** Answering this question can help predict how well a movie will perform in terms of audience reception.

## Exploratory Data Analysis (EDA) and Feature Selection
For our analysis, we selected several predictors including:
- **IMDB Rating**
- **Audience Rating**
- **Genre**
- **Critics Rating**
- **Number of IMDB Votes**
- **Oscar Wins** (for Best Actor, Best Actress, Best Director, and Best Picture)

### Summary of Response Variable (Audience Score)
- Median audience score: 65
- 25% of the movies have an audience score higher than 80
- 25% of the movies have an audience score lower than 46
- Very few movies score lower than 20 or higher than 90, indicating that extreme ratings are uncommon.

### Correlations
Through correlation analysis, we found that **IMDB rating** and **audience rating** have significant correlations with audience score. Some variables such as **critics rating** and **IMDB number of votes** did not significantly contribute to predicting audience score and were removed from the model.

## Model Development
We developed several models and refined them to increase the accuracy of predicting the audience score.

### Final Model (fit3)
The final model included **IMDB rating**, **audience rating**, and **genre** as predictors. Key results include:
- **IMDB Rating Coefficient (9.7844)**: A one-unit increase in IMDB rating leads to a 9.7844-point increase in audience score, holding other variables constant.
- **Audience Rating Upright Coefficient (20.3246)**: Movies with an Upright audience rating tend to have a 20.3246-point higher audience score compared to Spilled-rated movies.
- **Genre Effects**: For example, Animation films have an audience score that is 3.6812 points higher on average than Action & Adventure films, while Art House & International films score 2.7199 points lower, after controlling for other variables.
- **R-squared (0.8847)**: The final model explains 88.47% of the variability in audience score.

## Prediction
We used our final model to predict the audience score for a movie in the test set—**Aliens**. By creating a new dataframe with the relevant attributes for this movie, we can predict how the audience is likely to rate it.

## Conclusion
Our model shows that a movie’s popularity, as measured by audience score, can be predicted using just three variables: **IMDB rating**, **audience rating**, and **genre**. The movie industry can apply similar techniques to estimate how future films might be received by audiences.

## Limitations
A major limitation of our model is that the sample size is relatively small, and the dataset is not fully representative of all movies. A larger, more diverse dataset could improve the model’s accuracy by capturing a wider range of variability in audience preferences.

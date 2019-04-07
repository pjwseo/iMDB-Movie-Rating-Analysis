# Key Factors in predicting iMDB Movie Scores
## By Paul Seo

### Purpose:
This being the first project since completing Udacity's Data Analyst Nanodegree program, I decided to pick one of the earlier projects in the program and improve it by using all techniques I learned through the program.

### Dataset:
This dataset was originally provided on Kaggle, which was obtained by Udacity to be used in their course as training material. Due to DMCA takedown, this dataset has been replaced with TMDB dataset and is no longer available. The iMDB dataset contains 10866 movies and 21 variables for each of these movies. 

Early on, I decided I wanted to work with quantitative values and trimmed the dataset down to 10 columns. After converting data into correct types, getting rid of movies with few reviews, removing movies with missing information, converting genres into number of genres, and renaming columns, I was left with 2,603 movies to work with.

### Summary of Findings:
I used seaborn PairPlot to initially diagnose the variables against each other. I took note of some interesting relationships here for future visualizations. I then used a histogram to see the distribution of movie scores, which resembled a normal distribution with a mean of approximately 6.32 (score out of 10). I then moved onto bivariate plots, starting with viewer score against movie's budget. No meaningful relationship was found here and same for movie revenue. Plotting viewer score against release year of the movie and also against the number of genres returned no meaningful relationships. However, I was able to find moderate positive correltion between viewer score and vote count (0.396), and viewer score and movie runtime (0.382).

I tested all variables for multicollinearity, and moved onto multiple linear regression with vote count and movie runtime in predicting movie score. The linear model could explain 97.1% of variability in movie ratings. Both variables were found to be statistically significant factors and I calculated every 1 vote to contribute to 0.00008 increase in movie score and every 1 minute of a movie to contribute 0.055 in movie score.

### Conclusion:
In this analysis we took a look at the effect of various movie metrics on its iMDB viewer rating. Out of budget, revenue, release year, vote count, # of genres, and runtime, only movie runtime and vote count shows moderate positive correlation with viewer rating. The strength of their effect was found through linear regression.

In the future I would like to revisit this dataset to look at the effect of nominal variables on the viewer rating, it'll be really interesting if we could find actors, actresses, and directors who are more likely to generate a higher movie rating on iMDB.

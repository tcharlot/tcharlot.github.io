---
layout: post
title: Project 6 Blog
---



Summary

Given the text of an IMDB review and some attributes of the film being reviewed, I have built several models to predict the numeric rating of the review.

To approach this problem, I used all reviews from IMDB's top 100 movies that have a non-null rating attached to them. The models incorporate the words or word pairs that best differentiate between reviews, along with the movie's genre(s), release year and runtime as features.

A major weakness of this dataset is that its distribution is hugely skewed to high ratings, as we would expect when selecting ratings of only the top movies. To demonstrate the extremity of this skew, the average rating in our dataset is 8.44 (on a scale of 1 to 10), the 25th percentile is a rating of 8 and the 50th percentile is a rating of 10.

Basic Decision Tree classifiers perform poorly: this is better treated as a regression problem because we want to be as close to the numeric rating (1-10) as possible.

I found that a Random Forest Regressor and Extra Trees Regressor perform the best of the models considered. When tested on simulated out-of-sample data, they have RMSE of 5.0 and 4.91 respectively. However, all the models tend to overestimate ratings more often than they underestimate, and thus are ineffective at predicting low ratings. This is likely a consequence of the skew of our dataset to high ratings.

The next step to building a better predictive model for a review would be to use data of evenly distributed reviews across a sampling of movies with varying average ratings (it's also possible that the average rating impacts any given reviewer, something that we can't assess with our current dataset). Since Random Forest and Extra Trees performed the best out of the models I explored here, they would be a good place to start when modeling on this new dataset.

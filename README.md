# gamer-identification
This project was part of a Data Mining class at INSA Lyon. The project was realized by 3 Computer Science students: Chanèle Jourdan, Guilhem Baissus and me.

For a direct visualization of our work and a more detailed explanation, you can look at the following Kaggle notebook: https://www.kaggle.com/chanelejourdan/jcg-starcraft-2-prediction-challenge-2020

## Goal
The goal of this project was to learn to work with data, by cleaning it, thinking about the features importance and selecting the correct algorithms to apply.
This project was part of a Kaggle competition (https://www.kaggle.com/c/starcraft-2-player-prediction-challenge-2020) in which the goal is to correctly classify the gamers of the Starcraft 2 video game, using the different keys pressed on a keyboard by the gamer and a window of time for each key. 

## Different steps

First of all, we think that the most useful information happens in the first seconds of the game. Indeed, by having the timing and different keys, the beginning of the game is critical in detecting patterns which will make it possible to identify the correct gamer, so we consider only the 120 first seconds of each game.

In the notebook, we go through the following steps:
- Loading the data
- Data preprocessing and visualization
  - Extracting features
  - Cleaning the data
  - Solving the unbalanced class problem
  - Creating the dataframe
- Dimensionality reduction
  - Feature selection
  - Feature extraction
- Building a model and prediction
- Results 
- Conclusion

## Conclusion

|With new features|With duplication|Dim.Reduction    | Features' number                                  | RESULT            |
|-----|-----|-----------------------|---------------------------------------------------------|------------|
|No|No|No|36|0.897|
|Yes|No|No|62|0.897|
|No|Yes|No|36|0.897|
|No|Yes|Feature importance|19|0.885|
|No|Yes|Feature importance|11|0.841|
|No|Yes|Univariate selection |18|0.879|
|No|Yes|Univariate selection |13|0.829|
|No|Yes|Low variance|16|0.868|
|No|Yes|Low variance|?|?|
|No|Yes|PCA|20 new|0.879|
|No|Yes|PCA|13 new|0.868|

Here’s a summary of the results of all the models we’ve tested.

* 1st line: Our initial model without any dimensionality reduction has a result of 0.897
* 2nd line: By adding features we don’t have a better result so for the others tries we didn’t keep it since we want the reduce the dimension, so it wouldn’t makes sense.
* 3rd line: By duplicating data we have a similar result too.

About dimensionality reduction: 
* For the feature selection, we tested each method two times, keeping more or less features. We see that when we keep around 17-20 features, according the method, it reduces our results by only 0.02, and that dividing almost by two our number of features which is a really interesting result. 
* For feature extraction, with the PCA method, even taking a third of our features’ number, we still have good results.

Finally, if we had to keep only one model in this project we would anyway take the one without any dimensionality reduction because we think that we don’t really have a problem of time compilation or memory space in our case, and we’re not in a situation of over fitting. So we don’t really have an interest in reducing the dimension.
But we showed, and that was our objective, that it’s possible to gain lots of benefits by reducing dimension in others situations with a really big amount of features. (And of course there’re a lot of others methods to do that, we've here presented only 4 possibilities)

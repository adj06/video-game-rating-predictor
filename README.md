# video-game-rating-predictor

In this project I try to predict a video game's **critic score** (out of 100, from Metacritic) using basic information about the game: its platform, genre, age rating, release year, sales and user reviews.

I built it to practise the full machine learning process from start to finish: loading data, cleaning it, exploring it, training models and checking how well they work.

## My approach

I kept the code as simple as possible on purpose. Every step follows the basic examples in the official [pandas](https://pandas.pydata.org/docs/) and [scikit-learn](https://scikit-learn.org/stable/) documentation, and the notebook links to each page I used. My goal was to understand and explain each step clearly, rather than build the most accurate model possible.

Each section of the notebook starts with a short paragraph explaining what I did and why, so you can follow it without being a data science expert.

## What the notebook does

1. **Loads the data** and takes a quick look at it: the first rows, column types and missing values.
2. **Cleans the data.** Some user scores say `"tbd"` instead of a number, so I turn those into missing values. Then I remove any rows that still have missing values.
3. **Explores the data** with three charts: how critic scores are spread out, the average score per genre, and user score vs critic score.
4. **Prepares the features.** Text columns like `Platform` and `Genre` become 0/1 columns, and the data is split into 80% for training and 20% for testing.
5. **Trains two models.** I compare a simple one (Linear Regression) with a more complex one (Random Forest) to see if the extra complexity is worth it.
6. **Checks the results** using the scores below, a predicted vs actual chart, and a chart of which features matter most.

## Results

- **MAE (mean absolute error):** on average, how many points off a prediction is.
- **R²:** 1 means perfect predictions, and 0 means no better than always guessing the average score. 

## Dataset

I used the [Video Game Sales with Ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings) dataset from Kaggle. It combines sales figures from VGChartz with critic and user scores from Metacritic, for games released up to December 2016.

To run the notebook, download the CSV and save it as `data/videogamesales.csv`.

## How to run it

```bash
git clone https://github.com/<your-username>/video-game-rating-predictor.git
cd video-game-rating-predictor
pip install -r requirements.txt
jupyter notebook video_game_rating_predictor.ipynb
```

Then run all the cells from top to bottom.

## Tech used

Python, pandas, scikit-learn, matplotlib, Jupyter

## Limitations and next steps

The biggest limitation is missing data. About half the games have no critic score, so many rows were removed. The model also needs user reviews, which means it can't predict a score for a game that hasn't been released yet.

If I took this further, I would:
- fill in missing values instead of removing rows
- tune the Random Forest's settings
- try predicting scores without using user reviews

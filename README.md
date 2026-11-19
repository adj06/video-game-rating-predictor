# Video Game Rating Predictor

This project is about using machine learning to predict a video game's **critic score** (out of 100) on Metacritic.

I use information about each game, such as its platform, genre, age rating, release year, sales and user scores to try and predict its critic score.

I built this project to learn how machine learning works, from preparing the data to training models and checking their results.

## My Approach

I wanted to keep the project simple and easy to understand. I followed examples from the official [pandas](https://pandas.pydata.org/docs/) and [scikit-learn](https://scikit-learn.org/stable/) documentation to help me with each step.

I also added short explanations throughout the notebook to explain what I was doing and why.

## What the Notebook Does

1. **Loads the data:** I load the dataset and look at the first few rows, column types and missing values.
2. **Cleans the data:** Some user scores are marked as `"tbd"` instead of having a number. I replace these with missing values and remove rows that still have missing information.
3. **Explores the data:** I create three charts to look at critic scores, compare average scores between genres and see how user scores compare with critic scores.
4. **Prepares the data:** I convert text columns such as `Platform` and `Genre` into numerical values so the models can use them. I then split the data into 80% for training and 20% for testing.
5. **Trains two models:** I use Linear Regression and Random Forest to see which one makes better predictions.
6. **Tests the models:** I compare their results using MAE and R² scores. I also create charts to compare predicted scores with actual scores and show which features have the biggest impact.

## Results

I use two main measurements to check how well the models perform:

- **MAE (Mean Absolute Error):** Shows how far the predictions are from the actual critic scores on average. A lower score is better.
- **R²:** Shows how well the model can predict the scores. A value closer to 1 means the model is doing a better job.

## Dataset

I used the [Video Game Sales with Ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings) dataset from Kaggle.

It contains video game sales figures from VGChartz, along with critic and user scores from Metacritic. The dataset includes games released up to December 2016.

To run the notebook, download the CSV file and save it inside a folder called `data` as `videogamesales.csv`.

## How to Run It

```bash
git clone https://github.com/<adj06>/video-game-rating-predictor.git
cd video-game-rating-predictor
pip install -r requirements.txt
jupyter notebook video_game_rating_predictor.ipynb
```

Once the notebook opens, run all the cells from top to bottom.

## Technologies Used

- Python
- pandas
- scikit-learn
- matplotlib
- Jupyter Notebook

## Limitations and Future Improvements

One of the main problems with the dataset is that many games are missing critic scores. Around half of the games don't have a critic score, so I had to remove a lot of rows before training the models.

Another limitation is that the model uses user scores to make predictions. This means it cannot predict the critic score of a game before people have played and reviewed it.

If I continue working on this project, I would like to:

- Find better ways to deal with missing data instead of removing so many rows.
- Try different Random Forest settings to improve its predictions.
- Train another model without using user scores, so it can predict critic scores using information available before release.
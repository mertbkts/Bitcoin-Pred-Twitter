# Bitcoin Price Prediction Using Twitter Sentiment Analysis

## How It Works?
![](https://i.imgur.com/w3OX4di.png)

## Purpose

The purpose of this study is to design and develop a DNN based deep learning model for prediction of future bitcoin prices while examining if there is a correlation between social media and cryptocurrencies. Even though Long short-term memory models are popular for time series prediction, Deep Neural Network was chosen for model because to focus on how social media affects cryptocurrency prices, rather than other factors.


## Dataset Description

Open-source dataset "Bitcoin 17.7 million Tweets and price" is used to train the model. This dataset contains the average sentiment of all tweets about bitcoin from 01/08/2017 until 21/01/2019. It also contains the financial data of bitcoin for that same period. This dataset contains 14 different values to use, such as opening price of bitcoin, number of negative tweets. There was some missing data for some specific days, but I removed all of the values belonging to those days by hand. I also removed some columns that I thought were not needed for my project. In conclusion, I just used the columns of "Count_Negatives", "Count_Neutrals", "Count_Positives", "Open" and "Close.

This dataset can be found at: 
www.kaggle.com/jaimebadiola/bitcoin-tweets-and-price?select=Data_To_Hourervals_no_filter.csv

## Model Visualization
![](https://i.imgur.com/aFQqtfI.png)

## Used Libraries
- Tensorflow
- Keras
- Sklearn
- Matplotlib
- Joblib
- Pandas
- Numpy

## How to use?

### Training
Train your own model by using "Training.ipynb". Just enter your dataset's path into the following code, and then execute. You can also skip this process. All you have to do is using "model.h5" and "scaler.bin" files from main.

```
dataset = pd.read_csv(
    "/content/drive/MyDrive/TwitterBitcoinTahminSistemi/Dataset/TwitterDataset.csv" , delimiter=';')
dataset.head()
```

### Prediction
Use "Prediction.ipynb" to predict the bitcoin price after an hour. If you don't want to train your own model, you can use already trained model "model.h5" and "scaler.bin" from main.

#### 1-) Enter your model's and scaling parameter's path into the following code.
```
def prediction(Negative, Neutral, Positive, Open ):
  model = load_model(# Your model's path)
  scaler=load(# Your scaling parameter's path)
```
#### 2-) Enter your values to predict.

```
# Please enter values in such way : prediction(Number of Negative Tweets, Number of Neutral Tweets, Number of Positive Tweets, Current Bitcoin Value)
prediction(148,200,200,2980.81)
```
#### 3-) Execute.
The result:
```
1/1 [==============================] - 10s 10s/step
[[3000.3662]]
```

## Conclusion
Two metrics used to measure accuracy in this project. Mean absolute error of the model is 98 and mean absolute percentage error is 1.47%. You can also examine model's training history from the following figure:
![](https://i.imgur.com/7GHgVvn.png)

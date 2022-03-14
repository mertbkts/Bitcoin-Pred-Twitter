# Bitcoin Price Prediction Using Twitter Sentiment Analysis

## How It Works?
![](https://i.imgur.com/w3OX4di.png)

## Purpose

The purpose of this study is to design and develop a DNN based deep learning model for prediction of future bitcoin prices while examining if there is a correlation between social media and cryptocurrencies. 


## Dataset Description

Open-source dataset "SARS-COV-2 Ct-Scan Dataset" is used to train the model. This dataset contains 1252 CT scans that are positive for SARS-CoV-2 infection (COVID-19) and 1230 CT scans for patients non-infected by SARS-CoV-2, 2482 CT scans in total. CT scans belong to real patients in hospitals from Sao Paulo, Brazil.

This dataset is can be found at: 
www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset

## Model Visualization
![](https://i.imgur.com/Dxyh7u9.png)

## Used Libraries and Tools
- Tensorflow
- Keras
- Sklearn
- Imutils
- Matplotlib
- Numpy
- OpenCV
- VGG19
- Pathlib

## How to use?

### Training
Train your own model by using "Model_Training.ipynb". Just enter your dataset's path into the following code, and then execute. You can also skip this process. All you have to do is using "model.h5" and "weights.hdf5" that is ready for prediction.

```
dataset= # Your dataset's path
```

### Prediction
There are 2 ways to predict your own image. You can either use "Predict_An_Image.ipynb" to predict a single image, or use "Predict_Multiple_Images.ipynb" to predict multiple images in a file. If you don't want to train your own model, you can use already trained model "model.h5" and "weights.hdf5".

#### 1-) Enter your model's and weight's path into the following code.
```
model = keras.models.load_model(#' Please enter your model's path here')
model.load_weights(#' Please enter your weight's path here')
```
#### 2.1-) If you are using "Predict_An_Image.ipynb"

Enter your image's path into the following code.
```
ImagePath = #' Please enter the path of the image you want to predict'
```

#### 2.2-) If you are using "Predict_Multiple_Images.ipynb".

Enter your folder's path that contains CT images into the following code.
```
path = #' Please enter the path of the folder that contains images you want to predict'
imagePaths = list(paths.list_images(path))
```
#### 3-) Execute.

## Conclusion
The final accuracy of the model is %88. You can also examine model's training history from the following figures:
![](https://i.imgur.com/7GHgVvn.png)
![](https://i.imgur.com/Prk1ha5.png)

## Citation

```
Soares, Eduardo, Angelov, Plamen, Biaso, Sarah, Higa Froes, Michele, and Kanda Abe, Daniel. "SARS-CoV-2 CT-scan dataset: A large dataset of real patients CT scans for SARS-CoV-2 identification." medRxiv (2020). doi: https://doi.org/10.1101/2020.04.24.20078584.
Angelov, P., & Soares, E. (2020). Towards explainable deep neural networks (xDNN). Neural Networks, 130, 185-194.
}
```

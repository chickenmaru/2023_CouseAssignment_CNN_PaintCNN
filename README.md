
# 📘 Overview

This project's objective is to train a Convolutional Neural Network (CNN) to identify the painter of a given artwork. The model is developed to participate in a challenge to guess the painter of a collection of artworks. The dataset used is the "Best Artworks of All Time" from Kaggle. The project trains a CNN from scratch to classify paintings from 50 different artists.

# ⚙️ Training Flow

The training process is detailed in the Jupyter Notebook, and it follows these main steps:

1.  **Data Acquisition and Preparation**:
    * The dataset, which includes `train_resized/`, `test_resized/`, and `artists.csv`, is downloaded and unzipped. The `artists.csv` file provides information about the 50 artists, including their names, genres, and the number of paintings they have in the dataset.
    * The project emphasizes data preprocessing, as labels are embedded in the image filenames (e.g., `Claude_Monet_22.jpg`) and must be extracted programmatically. Artist names are mapped to numerical labels, and these are then converted into a 50-dimensional one-hot encoded vector.
    * All images are resized to a uniform size of 128x128 pixels and normalized to a range of \[0, 1] for consistent model input.
    * The dataset is shuffled and split into a training set (80%) and a validation set (20%).

2.  **Model Architecture**:
    * The model is a custom-built ResNet-like CNN architecture, as per the project constraints to avoid using pre-trained models via transfer learning.
    * The model consists of several convolutional layers, batch normalization, ReLU activation, average pooling, and residual blocks to improve training stability and performance.
    * The model concludes with a dropout layer to prevent overfitting, a flatten layer, and a dense layer with a softmax activation to output probabilities for the 50 classes.

3.  **Training and Evaluation**:
    * The model is compiled using the 'adam' optimizer and 'categorical\_crossentropy' loss, with 'accuracy' as the evaluation metric.
    * The model is trained for 40 epochs on the training data, with performance monitored on the validation set.

# 📊 Results

After 40 epochs, the model achieved the following performance on the test dataset:

* **Test Loss**: 2.8653
* **Test Accuracy**: 46.83%

The project also includes a function to predict the author of a single image, taking an image as input and outputting the name of the predicted artist.

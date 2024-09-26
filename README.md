# Videogame Video Classification
This Artificial Neural Network (ANN) is designed to classify videogame videos into 21 different classes (videogames)! It was specifically developed for [Clivy](https://github.com/juanmartin8a/Clivy) to automate videogame video classification when uploading a clip.

## Model
This AI model makes use of two models:
  - ### Feature Extractor:
    Extracts a high-dimensional vector (image embedding) for each frame using the ResNet101 convolutional neural network (CNN) architecture which was trained on a tailored dataset to classify images into 21 different videogames.
    
    **Model**: [Google drive link](https://drive.google.com/file/d/1pBWPHWTvzMKZa9pcByVRwIxGbFPWWzN0/view?usp=sharing)
    
    **Dataset used for training**: [Kaggle link](https://www.kaggle.com/datasets/juanmartinzabala/videogame-image-classification)
  - ### Sequence Classifier:
    Processes the sequence of embeddings and assigns a videogame class to the entire video.

    **Model**: *Not available :/*
    
     **Dataset used for training**: [Kaggle link](https://www.kaggle.com/datasets/juanmartinzabala/videogamesvideosdataset)

Both models were trained on Google Colab's free tier, limiting the time and computing power used to train the models.


## Model Workflow
The model works with a 4 step approach:
  1. ### Data pre-processing
      For every input video, 25 frames are extracted for processing.
  
      Only 25 frames are used for several reasons including:
        - Less computing power being used (I was broke (as of today 23 - 09 - 2024 I am still broke :') ) and couldn't afford anything other than the free tier).
        - Simplicity by having a uniform input shape.
        - 25 frames can still capture good data :D

  2. ### Feature extraction
      Frame information is extracted as an image embedding using the trained RESNET101 convolutional neural network. This is done for all 25 frames.

  3. ### Sequence modeling
      The embeddings are processed by a Long Short-Term Memory (LSTM) recurrent neural network (RNN) to capture temporal data across frames.

  4. ### Classification
      The output from the RNN is used to assign the processed video to 1 of the 21 videogames. This and the previous step are a single ANN.

## Disclaimer
Unfortunately, I was unable to find the weights for the Sequence Classifier, I probably deleted them long ago :(. However, you can get your own weights by training the model using the [jupiter notebook (videogame-video-classiification-train.ipynb)](https://github.com/juanmartin8a/Videogame-Video-Classification/blob/main/videogame-video-classiification-train.ipynb) provided in this repository and the dataset that can be found in this [Kaggle link](https://www.kaggle.com/datasets/juanmartinzabala/videogamesvideosdataset) :D

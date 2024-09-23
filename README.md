# Videogame Video Classification
This Artificial Neural Network (ANN) is designed to classify videogame videos into 21 different classes (videogames)! It was specifically developed for [Clivy](https://github.com/juanmartin8a/Clivy) to automate videogame video classification when uploading a clip.

## Model Workflow
The model works with a 4 step approach:
  1. ### Data pre-processing
      For every input video, 25 frames are extracted for processing.
  
      Only 25 frames are used for several reasons including:
        - Less compute being used (I was broke and couldn't afford compute).
        - Simplicity by having a uniform input shape.
        - 25 frames can still capture good data :D

  2. ### Feature extraction
      Frame information is extracted as a high-dimensional vector (image embedding) using the ResNet101 convolutional neural network (CNN) architecture which was trained on a tailored dataset to classify images into 21 different videogames. This is done for all 25 frames.

  3. ### Sequence modeling
      The embeddings are processed by a Long Short-Term Memory (LSTM) recurrent neural network (RNN) to capture temporal data across frames.

  4. ### Classification
      The output from the RNN is used to assign the processed video to 1 of the 21 videogames :)

## Model Components
This AI model makes use of two models:
  - ### Feature Extractor:
    Extracts feature embeddings for each frame using the pretrained CNN.
  - ### Sequence Classifier:
    Processes the sequence of embeddings and assigns a videogame class to the entire video.

Both models were trained on Google Colab's free tier, which limited the amount of computational resources available.

## Disclaimer
Unfortunately I was unable to find the weights for the Sequence Classifier, I probably deleted them long ago :(. However, I was able to find the weights for the ResNet101 model used as a feature extractor :D

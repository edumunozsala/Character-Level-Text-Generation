# Character-level text generator with Pytorch and Amazon SageMaker
## A guide on Recurrent Neural Network

In this repository we will be implementing a simple RNN character model with PyTorch to familiarize ourselves with the PyTorch library and get started with RNNs. The goal is to build a model that can complete a sentence based on a few characters or a word used as input. The model will be fed with a word and will predict what the next character in the sentence will be. This process will repeat itself until we generate a sentence of our desired length.

Once we have our model developed and tested, we create a second notebook to train the model in Amazon SageMaker, using a more powerful compute instance for longer training. Then we deploy our trained model as an endpoint on an instance in SageMaker. We can invoke this endpoint to make predictions on our model, and built a complete sentence from an initial string.

## The data set

First, we'll define the sentences that we want our model to output when fed with the first word or the first few characters. Our dataset is a text file containing Shakespeare's plays or books that we will extract sequence of chars to use as input to our model. Then our model will learn how to complete sentences like "Shakespeare would do".

This dataset can be downloaded from Karpathy's Github account: https://github.com/karpathy/char-rnn/blob/master/data/tinyshakespeare/input.txt.

## Problem description

The “character model” takes as an input a sequence of characters and it tries to predict the next one. In our case, the character were all the letters in lower case and the punctuations. It is simple and it will use the power of RNN to "remember" how to fill up an initial string to a given output size, copying or imitating the Shakespeare's books.

## Content
This repository contains the next source code files:
- char-level-text-generator-pytorch: This notebook shows how to download and preprocess the text data, create a batch data generator for sequences of data, define and build a simple encoder decoder architecture using LSTM units. We train this model with a toy dataset, just to test the model is working and finally we make some predictions (but not really good, the model is not trained).

- char-level-text-generator-pytorch-SageMaker: It is a demo on how to train a ML model in the framework Amazon SageMaker (using the model in the previous notebook). This model is very simple so you do not really need to launch a training job on SageMaker but it is intended for educational purposes. We also deploy our model as a service and make some predictions. This notebook requieres the folders:
    - train: here is where the training script is located. It also includes the model.py with the definition of our recurrent network and a utils.py with some helper functions to preprocess the text.
    - serve: this folder is needed to deploy the model, it contains a model.py and utils.py, the same as before, and a predict.py with the lines of code to make predictions on the model. 

## Contributing
If you find some bug or typo, please let me know or fixit and push it to be analyzed. 

## License

These notebooks are under a public GNU License.
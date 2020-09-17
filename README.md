# Character-level text generator with Pytorch
## A guide on Recurrent Neural Network

In this notebook we will be implementing a simple RNN character model with PyTorch to familiarize ourselves with the PyTorch library and get started with RNNs. The goal is to build a model that can complete a sentence based on a few characters or a word used as input.

The model will be fed with a word and will predict what the next character in the sentence will be. This process will repeat itself until we generate a sentence of our desired length.

# The data set

First, we'll define the sentences that we want our model to output when fed with the first word or the first few characters. Our dataset is a text file containing Shakespeare's plays or books that we will extract sequence of chars to use as input to our model. Then our model will learn how to complete sentences like "Shakespeare would do".

This dataset can be downloaded from Karpathy's Github account: https://github.com/karpathy/char-rnn/blob/master/data/tinyshakespeare/input.txt.

## Problem description

The “character model” takes as an input a sequence of characters and it tries to predict the next one. In our case, the character were all the letters in lower case and the punctuations. It is simple and it will use the power of RNN to "remember" how to fill up an initial string to a given output size, copying or imitating the Shakespeare's books.

## Contributing
If you find some bug or typo, please fixit and push it to be applied 

## License

These notebooks are under a public GNU License.
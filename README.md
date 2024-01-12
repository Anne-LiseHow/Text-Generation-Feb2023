## Text-Generation
A two-layer LSTM neural network has been implemented for text generation based on a Sci-Fi corpus. The data is available at: https://www.kaggle.com/datasets/jannesklaas/scifi-stories-text-corpus

### Pre-processing steps include:
* Split the text into sentences
* Remove hyperlinks
* Convert html character to string
* Convert contracted words to their full form
* Remove punctuations
* Remove single characters
* Remove multiple spaces
  
Since the data is quite large, a random subset of 5000 sentences was chosen, resulting in  10,407 unique words. The sentences were then tokenized and padded to be of the same length (30 words). The weights embedding matrix has been created from the GloVe pre-trained models of embedding dimension 200. 

### Hyperparameter Tuning
Hyperparameter tuning was performed using Bayesian Optimisation. The optimised model includes an Embedding layer, a LSTM layer with 640 units followed by a dropout layer with rate 0.5, another LSTM layer with 256 units followed by a dropout layer with rate 0.4, and lastly, a dense layer of 10,407 units. Optimizer used is Adam with a learning rate of 0.01. 

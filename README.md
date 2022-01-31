# Genre from lyrics recognition
 Repository dedicated to a project involving NLP analysis of lyrics for the purpose of genre classification for various songs.
 
 ## Objective
 Inquiries into understanding artistic drive have often been unsuccesful, as there is major unpredictability in human expression. However, recent exponential advancements in data storage and utilisation may help us better understand what artists convey by identifying patterns. Such is the case for genres which, whilst having strong musical foundations in terms of rythm, beat, instruments etc. cover a plethora of diversity when it comes to their lyrics. Therefore, we ought to ask the question: Can we predict a song's genre by only looking at its lyrics?
 
 There were previous attempts in this regard, some even performed on the same data (see section below), but most of them failed to achieve relevant performance standards. For comparison, a project [set with the same purposes](https://web.stanford.edu/class/cs224n/reports/final_reports/report003.pdf) has achieved a peak performance of ~68% accuracy on the predictions. Our main objective will be advancing the research further by passing this threshold. 

## Data
 The data was web-scrapped by [Anderson Neisse](https://www.kaggle.com/neisse) from a free to use [lyrics website](https://www.vagalume.com.br/), and has been uploaded [to kaggle](https://www.kaggle.com/neisse/scrapped-lyrics-from-6-genres?select=lyrics-data.csv). All upload rights and authorization for external use goes to the author.
 
 We have recorded the original data [in our own Original Data folder](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/tree/main/Capstone/Data/Original%20Data) for ease of access. All ulterior processed & enriched data derived can also be found [in the Data folder](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/tree/main/Capstone/Data/Processed%20Data).
 
 ## Approach
  We've decided to explore two different means of transforming the data into an interpretable, numerical context: vectorisation and sequentialisation. For the former, given the extensive memory capacity, we've used a common low-complexity technique, i.e. multinomial logistic regression. For the latter, we could explore more advanced deep techniques, namely neural networks. However, the expected lack of context between sentences (verses) in songs, unlike the case for texts designed for coherency such as novels or e-mails resulted in a self-imposed limitation of our approaches to simpler types of NN. We've therefore considered two models: An [LSTM RNN](https://en.wikipedia.org/wiki/Long_short-term_memory) (Long Short Term Memory - Recurrent Neural Network) and a simple [MLP](https://machinelearningmastery.com/when-to-use-mlp-cnn-and-rnn-neural-networks/#:~:text=Multilayer%20Perceptrons%2C%20or%20MLPs%20for,also%20called%20the%20visible%20layer.) (Multi-Layer Perceptron).
  
  Finally, all the models were individually considered with their benefits and drawbacks, and an ensemble was constructed. The [final algorithm]() can be found as the last notebook in our [main work]() folder.

# Genre from lyrics recognition1
 
 ## Objective
 Inquiries into understanding artistic drive have often been unsuccesful, as there is major unpredictability in human expression. However, recent exponential advancements in data storage and utilisation may help us better understand what artists convey by identifying patterns. Such is the case for genres which, whilst having strong musical foundations in terms of rythm, beat, instruments etc. cover a plethora of diversity when it comes to their lyrics. Therefore, we ought to ask the question: Can we predict a song's genre by only looking at its lyrics?
 
 There were previous attempts in this regard, some even performed on the same data (see section below), but most of them failed to achieve relevant performance standards. For comparison, a project [set with the same purposes](https://web.stanford.edu/class/cs224n/reports/final_reports/report003.pdf) has achieved a peak performance of ~68% accuracy on the predictions. Our main objective will be advancing the research further by passing this threshold. 

## Data
 The data was web-scrapped by [Anderson Neisse](https://www.kaggle.com/neisse) from a free to use [lyrics website](https://www.vagalume.com.br/), and has been uploaded [to kaggle](https://www.kaggle.com/neisse/scrapped-lyrics-from-6-genres?select=lyrics-data.csv). All upload rights and authorization for external use goes to the author.
 
 We have recorded the original data [in our own Original Data folder](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/tree/main/Capstone/Data/Original%20Data) for ease of access. All ulterior processed & enriched data derived can also be found [in the Data folder](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/tree/main/Capstone/Data/Processed%20Data).
 
 ## Approach
  We've decided to explore two different means of transforming the data into an interpretable, numerical context: vectorisation and sequentialisation. For the former engineering, given the extensive memory capacity, we've used common, low-complexity techniques, i.e. LogReg (Multinomial Logistic Regression) and RF (Random Forests) respectively. For the latter, we could explore more advanced deep techniques, namely neural networks.
  
  However, the expected lack of context between sentences (verses) in songs, unlike the case for texts designed for coherency such as novels or e-mails resulted in a self-imposed limitation of our approaches to simpler types of NN. We've therefore considered two models: An [LSTM RNN](https://en.wikipedia.org/wiki/Long_short-term_memory) (Long Short Term Memory - Recurrent Neural Network) and a simple [MLP](https://machinelearningmastery.com/when-to-use-mlp-cnn-and-rnn-neural-networks/#:~:text=Multilayer%20Perceptrons%2C%20or%20MLPs%20for,also%20called%20the%20visible%20layer.) (Multi-Layer Perceptron).
  
  Finally, all the models were individually considered with their benefits and drawbacks, and an ensemble was constructed. The [final algorithm](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/blob/main/Capstone/Portfolio/7%20-%20Algorithm%20%2B%20TDD.ipynb) can be found as the last notebook in our [main work](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/tree/main/Capstone/Portfolio) folder.
  
  ## Results
 Considering the implicit shortcomings of the data provided (namely size and imbalance), the LSTM proved to have potential on better suited data, but lacked performance on ours. On the other hand, the [LogReg implementation](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/blob/main/Capstone/Portfolio/4%20-%20Logistic%20Regression%202%20-%20Final%20Model.ipynb) achieved a remarkable performance of 75%, already surpassing the set objective; with similar performances from the [RF implementation](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/blob/main/Capstone/Portfolio/5%20-%20Random%20Forest.ipynb). 
 
 Moreover, the [MLP implementation](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/blob/main/Capstone/Portfolio/6%20-%20Neural%20Networks.ipynb) presented varied response in terms of how many words a song presented. Most new words would initially be transcribed as noise, to be later transformed into signal when a sufficient threshold for the minimum number of words in a song was succesfully met. This resulted in performances ranging from a worst of 36% to a best of 92%, which led us embrace an ensemble of our best performing models based on these criteria. The mathematical implications of this phenomenon are [better recorded here](https://www.mathcha.io/editor/4Qmgou4GfLpHld1wQoSWg9vYIGXngyxSlBw1GL).
 
  Overall, our final performance ranges from 75% - 92%, which makes the [proposed algorithm](https://github.com/Alex-Caian/Genre-from-lyrics-recognition/blob/main/Capstone/Portfolio/7%20-%20Algorithm%20%2B%20TDD.ipynb) better than the previous baselines. These numbers can be further improved, mainly by addressing the aforementioned issues with the data: size and class balance. The latter was especially damaging when it came to the Pop genre, and could be partially addressed by simply introducing more songs within the training. Our thorough performance gain analyses have indicated that variation across songs will be more than accounted for by our model, so simply feeding it more data would suffice for a continuous improvement.
  
  Lastly, this would only work until overfit is encountered. Methods to combat that would rely on more extensive insights into the structure of our chosen models, and finding a fit that could dynamically account for new data in a streamlining fashion _without_ reaching an overfit stage.
  
  ## Contact
 All rights for this work go to:
 
 [Alex Caian](https://github.com/Alex-Caian) - Contact at ac17176@alumni.bristol.ac.uk
 
 [Inès Rigaud](https://github.com/rigins) - Contact at rigaud.ines@gmail.com
 
 For questions regarding records or right of external use reference the contact points above.

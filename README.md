# Visualizing similarity across speeches about COVID19

The graph represents the similarity structure of 30 different speeches given by presidents and prime ministers of different countries during the COVID-19 pandemic of 2020. The only exception is the WHO Director-General's remarks at the media briefing on COVID-19 which was included in the analysis as a “neutral” reference point. 
### Data collection and pre-processing
The speeches transcripts were collected from official local government websites or newspapers. Speeches transcripts in a language different from english were translated into english using Google Translator. Each text was then cleaned from stop-words and lemmatised. A spreadsheed with the links to the original transcripts is available [here](https://github.com/RiccardoBarb/Covid19SpeechBubbles/blob/master/Sources.xlsx), the translated transcripts in text files can be found in [this](https://github.com/RiccardoBarb/Covid19SpeechBubbles/tree/master/txt) folder, organized by country name. A preprocessed version of the speeches is also available [here](https://github.com/RiccardoBarb/Covid19SpeechBubbles/tree/master/preprocessed)
### Speech vectors
The words in every speech were converted into vectors of 300 numbers (word vectors), obtained from the word2vec-GoogleNews-vectors model [1]. The numbers describe the model representations (previously learned on 3 million different words and phrases) of each word in the speech. The word vectors were then averaged to obtain a set of 30 vectors (speech vectors), representing the features of each speech [2]. Finally the similarity between each pair of speeches was estimated by calculating the cosine distance among averaged speech vectors.
### Similarity bubbles.
The position of each bubble in the graph and its distance from the others, reflect their degree of similarity. Bubbles that are close together represent speeches that are more similar to each other, while those far away represent speeches that are more different. Interestingly, European and South American speeches seem to cluster together more than the Asian ones.

![WordsOfPandemic](https://github.com/RiccardoBarb/Covid19SpeechBubbles/blob/master/WordsOfPandemic.png)

### References
* [1] [word2vec-GoogleNews-vectors](https://code.google.com/archive/p/word2vec/)
* [2] [Tomas Mikolov, Ilya Sutskever, Kai Chen, Greg Corrado, and Jeffrey Dean. Distributed Representations of Words and Phrases and their Compositionality. In Proceedings of NIPS, 2013](https://arxiv.org/pdf/1310.4546.pdf)

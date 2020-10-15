# Comment-Classifier

### Data: 
The given data consists of 6,182 comments collected from online forums. They are pre-labeled with values 1 (offensive comments) or 0 (neutral comments). The data set is split in training set which consists of 2,898 neutral comments and 1,050 offensive comments as well as test set consisting of 1954 neutral comments and 694 offensive. In the following examples you can see the two types of comments:

Insult: "Oh, you are such an idiot ..... you just confirmed that you can not read ... dumb @ rse!"
Neutral: "You get the gold star! The best post I've seen on here in months !! Hilarious ... Great job, Canadian! PS I think we need you to come down here.I’ll sponsor you !!

### Queries:

* Clean data: As a first step you must convert all characters to lowercase and remove characters such as punctuation, characters such as "\ n", "\ u0111" and generally symbols or urls if any.
* You will first use the classic NaiveBayes algorithm for classification (in this step you will convert the comments to word vectors using the sklearn library CountVectorizer).
* You will optimize Naive bayes: (1) by doing lemmatization, (2) by removing stop words, (3) by using bigrams (two-word phrases) instead of unique words, (4) by using Laplace Smoothing.
* You will then create a more complex feature table containing part-of-speech features and TF-IDF-based features.
* You will test all the features you have exported (part-of-speech and TF-IDF) on two additional different models: an SVM and a random decision forest.
* Apart from the above you can experiment with any method / feature you want in order to achieve the best possible results in the test set. The best possible model so far has an F1-score: 0.952.

### Summary of features to export
#### Part-of-Speech Based Features: 
Using the part-of-speech tagger provided by NTLK, tag each word in each comment with its part of speech (noun, verb, adverb or adjective) . Then calculate the percentage of specific tags for each text. That is, the frequency of each POS tag in each sample, calculated in terms of the total number of words in the sample. This way you will have 4 new attributes in each text, fractionAdverbs, fractionVerbs, fractionAdjectives, fractionNouns. The same procedure must be done in the test set.

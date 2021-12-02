# Modern-Data-Assignment

Stage 1: Data Gathering

Stage 2: Data Cleaning

Stage 3: Sentiment Analysis


# Stage 1: Data Gathering:-

Now that you have created a developer account and an app, you should have a set of keys to connect to the Twitter API. Specifically, you’ll have an
API key

1. API secret key

2. Access token

3. Access token secret


# Stage 2: Data Cleaning:- 

We shall go over several steps to clean the news dataset to remove the unnecessary content and highlight the key attributes suitable for the ML model.

### Step 1: Punctuation:-
The title text has several punctuations. Punctuations are often unnecessary as it doesn’t add value or meaning to the NLP model. The “string” library has 32 punctuations.

### Step 2: Tokenization:-
Tokenizing is the process of splitting strings into a list of words. We will make use of Regular Expressions or regex to do the splitting. Regex can be used to describe a search pattern.

### Step 3: Stop words:-
Now, we have a list of words without any punctuation. Let’s go ahead and remove the stop words. Stop words are irrelevant words that won’t help in identifying a text as real or fake. We will use “nltk” library for stop-words and some of the stop words in this library are :

### Step 4 : Lemmatize/ Stem:-
Lemmatization involves breaking a word down to its simplest form. This is somewhat similar to stemming which is used by many search engine libraries like solr, however generally can be more efficient.
For example, talked, talking, talk, are all forms of the lemma "talk".
This can be a useful tool for identifying the frequency that words appear in text.
For example, text that includes fishing, fished, and fish can all be lemmatized to identify that it contains three instances of "fish".
It can also be combined with PoS tagging to lemmatize just verbs, so for example, ignore instances of fish when used as a noun.

### Step 5: Other steps:-

Other cleaning steps can be performed based on the data. I have listed a few of them below,
1. Remove URLs
2. Remove HTML tags
3. Remove emoji
4. Remove numbers


# Stage 3: Sentiment Analysis


### 1. Word Cloud Visualization:- 

Many times you might have seen a cloud filled with lots of words in different sizes, which represent the frequency or the importance of each word. This is called Tag Cloud or WordCloud. For this tutorial, you will learn how to create a WordCloud of your own in Python and customize it as you see fit. This tool will be quite handy for exploring text data and making your report more lively.

### Sentiment Analysis:- 

Sentiment Analysis can be used to classify the sentiment of text. In the case of TextBlob it will classify it as a range from negative to positive, with neutral being in the middle.

In TextBlob, sentiment is represented by two numbers - polarity and subjectivity.

### 1. Polarity:

This represents how negative or positive the sentiment is, and is represented as a float value within the range:-

 1.) -1.0 (negative sentiment) to 1.0 (positive sentiment).

 2.)  0 would represent neutral sentiment.

### 2. Subjectivity:
This represents whether the sentiment is based on a trustworthy or verifiable source, or if is just an opinion, emotion, or judgement.
It is represented as float between 0.0 and 1.0, with 1 representing a more subjective (opinion based) sentiment.

TextBlob uses a rule-based approach to sentiment analysis, as opposed to a machine learning based approach. This has some limitations including the lack of factoring in context for words. It looks at the words and frequency to determine sentiment, not the context or placement of the words.
This may work fine for some domains and use cases, but may not give the desired results in other cases.

Now lets take a look at variations of the above sentence that it might consider less subjective. 
For example, I would consider the following sentence to be slightly less subjective but it did not:

No change in the subjectivity score above.
Replacing the sentence with "Yesterday we went to the movie theater and saw Star Wars. Everyone that saw it said it was very good.", also did not change the subjectivity score.
However, if all you are looking for is a threshold of polarity, then this may not matter.

You can also check the sentiment on individual sentence tokens rather than then entire blob. For example

Here we can see that the first sentence did not have any polarity or subjectivity associated with it - it was neutral sentiment. Which makes sense. And for the second sentence, we have our polarity and subjectivity scores as we saw above.

## Handling Negatives:

Above I changed the text to use a negative - It was not very good.
You can see from the polarity score that it recognized the negation of very good and now assigned it a negative polarity score to properly reflect a negative sentiment. 
However it now changed the subjectivity score. I'm not quite sure why "It was not very good" vs "It was very good" would have different levels of subjectivity.



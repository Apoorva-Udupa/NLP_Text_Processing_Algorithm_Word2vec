# NLP Text Processing and Word2Vec

This repository contains a Jupyter notebook that demonstrates various Natural Language Processing (NLP) techniques including text preprocessing, stemming, lemmatization, parts of speech tagging, named entity recognition, and the use of Word2Vec with the Google News dataset.

## Text Preprocessing

### Stemming
Stemming is the process of reducing a word to its word stem that affixes to suffixes and prefixes or to the roots of words known as a lemma. It is important in Natural Language Understanding (NLU) and NLP.

#### Porter Stemmer
The Porter Stemmer algorithm is one of the most common stemming techniques.

#### Disadvantages of Stemming
One major disadvantage is that it can change the meaning of words. For example, "history" can become "histori", which can alter the meaning.

#### REGEX Stemmer Class
NLTK has a `regexstemmer` class that allows easy implementation of Regular Expression Stemmer algorithms. It removes any prefix or suffix that matches the given expression.

#### Snowball Stemmer
The Snowball Stemmer is an improvement over the Porter Stemmer.

### Lemmatization
Lemmatization is similar to stemming but returns a valid word called "lemma", which has the same meaning as the original word. NLTK provides the `WordNetLemmatizer` class to perform lemmatization.

### Stop Words
Stop words are common words that are usually removed during text preprocessing to focus on significant words.

### Parts of Speech Tagging
Parts of speech (POS) tagging involves labeling words in a sentence as nouns, verbs, adjectives, etc.

### Named Entity Recognition (NER)
NER identifies and categorizes key information (entities) in text. For example, person names, locations, dates, and times.

## Word2Vec
Word2Vec is a popular word embedding technique. This notebook uses the Google News dataset to demonstrate Word2Vec.

### Key Functions
- `wv.get_vector(word)`: Gets the vector for a word.
- `wv.most_similar(word)`: Finds words most similar to the given word.
- `wv.similarity(word1, word2)`: Computes similarity between two words.

### Example Usage
```python
import gensim.downloader as api
wv = api.load('word2vec-google-news-300')

# Get vector for a word
vec_king = wv['king']

# Most similar words
wv.most_similar('queen')

# Similarity between two words
wv.similarity("king", "queen")

# Vector arithmetic
vec = wv['king'] - wv['man'] + wv['woman']
wv.most_similar([vec])

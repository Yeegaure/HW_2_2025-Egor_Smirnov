
The dataset "IMDB Dataset.csv" is too heavy to be downloaded to github repository, but it can be downloaded via the link: https://disk.360.yandex.ru/d/dhKpEgM4rQkLiQ
It needs to be added in the same folder, as the notebook, to run it correctly.


# Project Overview: Text Analysis of Song Lyrics and IMDB reviews Using NLP methods

This project explores **Natural Language Processing (NLP)** techniques applied to a small dataset of song lyrics. The goal is to compare different text‑representation methods, visualize their structure, and extract meaningful patterns from the vocabulary and semantics of the songs. The second part of the project consists in training BERT classifier to perform sentiment analysis for dataset of IMDB movies reviews

The project demonstrates how various vectorization and embedding models interpret the same text differently, and how these representations can be analyzed through clustering, dimensionality reduction, and frequency‑based visualizations.

---

## Objectives

- Preprocess and clean raw song lyrics  
- Represent text using multiple NLP models:
  - **CountVectorizer**
  - **TF‑IDF**
  - **Word2Vec**
  - Doc2Vec
- Visualize and compare the resulting feature spaces  
- Explore word frequencies, bigram patterns, and semantic similarity  
- Build intuitive visualizations such as heatmaps, t‑SNE plots, and word clouds
- clean and tokenize the dataset of IMDB movies reviews
- Construct embeddings of tokens form BertTokenizer
- Train BERT classifier on resulting tokens for 5 epochs to perform sentiment analysis for IMDB movies reviews

---

## Text Preprocessing

The dataset consists of three songs. Each song is cleaned and tokenized using:

- Lowercasing  
- Removing punctuation  
- Removing stopwords  
- Tokenization  
- Lemmatization  

This produces a clean corpus suitable for vectorization and embedding.

---

## Models Used

### **1. CountVectorizer**
Represents each song as a sparse vector of raw word counts.  
Useful for:
- Frequency analysis  
- Bigram extraction  
- Heatmap visualization  

---

### **2. TF‑IDF**
Represents each song using weighted word importance.  
Highlights:
- Distinctive words per song  
- Differences in vocabulary emphasis  
- Weighted bigram analysis  

---

### **3. Word2Vec**
Learns dense semantic embeddings for each word.  
Used for:
- Word similarity queries  
- t‑SNE visualization of semantic clusters  
- Average song embeddings  
- Bigram frequency analysis  

---

## Visualizations

### **1. t‑SNE Embeddings**
t‑SNE is applied to:
- TF‑IDF word vectors  
- CountVectorizer word vectors  
- Word2Vec embeddings  

---

### **2. Heatmaps**
Heatmaps are generated for:
- CountVectorizer matrix  
- TF‑IDF matrix  
- Word2Vec average song embeddings  

---

### **3. Word Clouds**
A word cloud visualizes the most frequent words across the entire corpus.

---

### **4. Frequency Bar Charts**
For each model, the project plots:
- Top N most frequent words  
- Bottom N least frequent words  
- Top and bottom bigrams 

This helps compare how different models treat vocabulary.

---

## Bigram Analysis

The project extracts and visualizes bigrams for all methods:

- **CountVectorizer**: direct bigram counts  
- **TF‑IDF**: weighted bigram importance  
- **Word2Vec**: bigram frequency extracted from tokenized text  

This reveals common phrase patterns across songs.

---

## Word Similarity

Using cosine similarity and Word2Vec’s similarity search, the project identifies:

- Words that appear in similar contexts (Count/TF‑IDF)  
- Words that share semantic meaning (Word2Vec)  

---

## BERT classifier

### Tokenize text
- clean reviews by removing .html tags
- lowercase all words
- remove punctunation and special symbols like '\n'
- remove stopwords
- tokenize using BertTokenizer

### BERT model
- split data by train and vaidation datasets
- BERT classifier model on GPU
- train for 5 epochs (use free google colab GPUs)
- optimizer - Adam
- loss - CrossEntropyLoss()
- evaluate classficication quality on train and validation datasets with accuracy, precision, recall and F1-score metrics

## Technologies Used

- Python  
- NumPy, Pandas  
- Scikit‑learn  
- Gensim  
- Matplotlib, Seaborn  
- WordCloud
- nltk
- Pytorch

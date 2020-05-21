
## Overview
This project was made as part of the Microsoft Student Accelerator program 2020.

I enjoy reading books in my spare time so i decided to create this project to automate the process of reading book blurbs to classify its genres. Multi label classification is also a prominent area of research in Machine Learning so I was intrigued with the challenge of combining text analysis and multi label prediction. 

I've also added explanations for the code in the Jupyter notebook.

**Approach:** 
To build a model that accurately predicts multiple book genres, we will be training three different models and comparing them. 
 - Random Forest Classifier
 - Logistic Regression Classifier (Incorporated with OneVsAll)
 - Deep Feedfoward Neural Network

## Table of contents
* [Preprocessing](#preproccessing)
* [Training](#training)
   * [Baseline Model](#baseline-model)
  * [Random Forest](#random-forest)
  * [Logistic Regression](#logistic-regression)
  * [Neural Network](#neural-network)
* [Testing functions](#testing-functions)
* [Evaluation](#evaluation)
* [Setup & Dependencies](#setup)
*  [Practicality & Improvements](#future)

## Dataset:
**Source:** Carnegie Mellon University<br/>
**Name:** CMU Book Summary Dataset<br/>
**Books:** 16,559<br/>
**Metadata:**

 - Wiki ID
 - Freebase ID
 - Book Title
 - Book Author
 - Publication Date
 - Genres

## Preproccessing
### Data preprocessing:
**Extract useful data:** We will only be using 'Title', 'Genres' and 'Summary' for our models.<br/>
**Missing values:** Removed all missing values from our dataframe (3718 were found in the 'Genres' column).<br/>
**Freebase Tags:** To remove freebase tags, we import the data using json.loads<br/>
**Low frequency Genres:** Removed over 150 genres which contained less than 50 books, merged several subgenres into their respective genres (i.e Speculative Fiction -> Fiction).

### Text preprocessing:
**To clean the text features, we will:**

 1. Change all characters to lower case
 2. Remove any numbers from text
 3. Remove white spaces
 4. Remove punctuation (with String library)
 5. Remove words with less than 3 characters
 6. Remove stopwords (with NLTK)

### Preparing data for models:
**Genres:** Since there are multiple genres to be classified, we will be using a multi label binarizer 

**Text data:** For the Logistic Regression and Random forest classifier, we will be using a TF-IDF vectorizer with a threshold of 0.8 and using a maximum of 10,000 features. 

For the Neural Network, we will create a work index using Keras's Tokenizer where the most frequent words will appear first. We will also convert the summaries into sequences and pad them to a max length of 500 characters. 

**Splitting Data:** We will be using the typical 80-20 train/test split to train our models.

## Training
To compare our models, we will be using their f1 scores which is the balance between precision/recall since there are multiple labels to be classified. We will also be using the **micro average** since there is a significant class imbalance. 
### Baseline model:
For our baseline model, we will simply take the most frequent genre (Fiction:   
4191) and since there are now 11282 books in our dataset, the baseline accuracy will be 4191/11282 = 37%. Note that accuracy is only with one genre so precision, recall and f1 score are not applicable. With that in mind this is purely for observation.
### Random Forest:

### Logistic Regression:

### Neural Network:

## Testing Functions

	
## Evaluation


## Setup 


## Future


# "Keep it Secret, Keep it Safe! Preserving Anonymity by Subverting Stylometry" by Robin Camille Davis

A 1963 study examined The Federalist Papers to determine authorship of some documents.
Using word counts, they determined all unaccounted papers were probably authored by Madison.


## Stylometry

The statistical measurement of an author's writing style.


## Text analysis with Python

To get started you only need:

* Corpus of text
* Machine learning library

`scikit-learn` is a well-documented, widely used library for machine learning and text analysis.


## Classification

Essentially categorization into different groups based on some criteria or features.
Stylometry uses writing style features to categorize into different author buckets.
The corpus of known authors is used to classify a document by an unknown author.

Feature examples:

* Word/term frequency
* Word length
* Sentence length
* Punctuation frequency

Frequency is better than count since it accounts for the total length of the document being considered.

The basic workflow is:

1. Train a classifier on an existing corpus of labeled texts
1. Use the classifier to predict the label for an unlabeled text


## Applications

Law enforcement can use writing style as a biometric to determine authorship.
Defensive stylometry can flag emails or other publications as deviating from an author's normal style.
It can also detect plagiarism by calculating similarity to existing works.


## Anonymity

Remaining anonymous is often desirable in social activism, writing under a pseudonym, whistleblowing/journalism.
Privacy is a concern and people have good reasons not to be outed by their own writing style.
It's difficult and slow to imitate someone else's writing style.
You could run the text through a translation tool, but meaning can get lost or your style could be preserved as these tools improve.
Another strategy is to use stylometric features to your advantage;
change the frequency of word length, sentence length, word choice in your writing.


## Nondescript tool

Takes in your writing sample as well as a message to anonymize, and suggests ways to remove featureful words via synonym suggestion.
Using it recursively can help reduce overall similarity to prior works.

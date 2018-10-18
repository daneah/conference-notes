# "Building an Ungrammatical Corpus by Corrpution" by Pablo Gonzalez Martinez


## Language models and grammaticality

* Language models check if output of a system is likely a string
* Grammaticality is about whether a string of words is a sentence or not
* Language model compares likelihood of several candidates to see which looks most like the language in question
* Grammaticality returns a binary answer about grammatical or not


## Negative evidence

* Negative evidence is input that violates the rules of a language
* Used by linguists to pry at the structure and rules of language
* Example: "I like oranges" vs "I oranges like"
* Children don't receive/employ negative evidence often but still learn language quickly


## N-gram approach vs. neural networks

* N-gram models don't generally accept negative evidence but neural networks can benefit from this approach
* Binary classifiers using convolutional neural networks can receive positive and negative evidence in training and
  use the learning to classify unknown data


## Approach

* Manually supplied negative evidence can be used, but there's not a sufficient amount of data
* Supply specific type of ungrammatical data where the location of the problem is known
* Use corpus of grammatical data and corrupt it deliberately:
  * Gender and number disagreement, i.e. carros roja
  * Verb conjugation, i.e. past imperfect instead of present
  * No subject or no verb

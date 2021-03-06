## Chompsky - Wikia NLP Library ##
![Imgur](http://i.imgur.com/uBV0r.jpg)

These are scripts that use data available on Wikia for natural language processing.
The results of these scripts can be reused for a variety of purposes 
(e.g. improved search relevance, customer support, new features)

This is named after a goofy drawing I made one time of Noam Chomsky.
And also because it chomps through text. Take your pick.
This project in no way endorses Chomsky's views on linguistics. In fact, it flouts it.

Written for the Wikia December 2012 Hackathon

## Dependencies ##
* [NLTK](https://github.com/nltk/nltk)
* [NLTK Contrib](https://github.com/nltk/nltk)
* [Pattern](https://github.com/clips/pattern)
* [Summarize](https://github.com/thavelick/summarize)
* [ARKRef](http://www.ark.cs.cmu.edu/ARKref)
* [OpenNLP](http://opennlp.sourceforge.net/)
* [WordNet](http://wordnet.princeton.edu/wordnet/download/current-version/)
* [Stanford CoreNLP](http://nlp.stanford.edu/software/corenlp.shtml)

## Scripts ##

* **get-sentiment.py** -- A script that accesses text from Solr for a given wiki and namespace
and determines the average sentiment (positive/negative) and objectivity (subjective/objective).
* **get-named-entities.py** -- A script that accesses all named entities for a document
* **summarize-doc.py** -- Summarizes the text of one or more documents
* **ark-coref.py** -- Uses ARKRef to perform NER on a specific document
* **get-readability.py** -- Performs a number of readability tests on a provided document

## The Coref Pipeline ##
This is a set of scripts respnsible for extracting named entities out of Solr text and and storing in MongoDB. This includes:
* **coref/coref-write-files.py** -- writes a raw file per wiki in a folder named after the wiki host
* **coref/coref-attach-files.py** -- attaches a batch of files to Stanford CoreNLP's parser
* **coref/coref-transform-xml.py** -- iterates over a directory, reads all XML files, and extracts, transforms, and loads the data into MongoDB
* **coref/coref-etl-batch.py** -- attaches ETL scripts to particular directories
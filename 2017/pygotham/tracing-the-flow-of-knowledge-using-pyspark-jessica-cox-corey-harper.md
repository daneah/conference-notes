# "Tracing the Flow of Knowledge Using PySpark" by Jessica Cox and Corey Harper, Elsevier


## Citation networks

How many times are authors citing each other?
Cardinality is not a great measure of positive influence without factoring in sentiment analysis of citations, i.e.
a work could be cited many times but the majority of those citations could be pointing out issues in the work's quality


## Architecture

Databricks and PySpark


## Processing

Example data: corpus of nobel prize winners
1. Gather all citations
1. Limit scope of those works
1. Desired input data set

* Look at next and previous sentences in the same paragraph around the citation
* Clean up text via regex, case normalization
* Filter by subject matter hierarchy


## Analysis

* Look at age of citations; newer citations are sometimes better especially in quickly evolving fields since data can
  get stale
* Look at location of citations; citations used in introduction may be prior works, citations elsewhere may be
  supporting works, etc.
* Look at subject matter hierarchy location; determine if citations are really relevant to the field in question

# "1 + 1 = 1 or Record Deduplication with Python" by Flávio Juvenal

Real-world data is a mess;
it's either unstructured or many records are duplicates with slight variation.
This arises from spelling, abbreviations, typos, or mistaken names.

Record linkage is the idea of joining records that represent the same information.
It uses fuzzy matching on record fields to determine similarities.


## Fuzzy string comparison

* Jaro-Winkler string similarity
  Favors leading character similarity
* Geocode street addresses to convert to latitude/longitude and compare things that are close in location
  Can remove variation in ZIP code, misspellings, abbreviations


## Preprocessing

* Clean restaurant names to only alphanumerics
* Geocode addresses to get ZIP and latitude, longitude


## Identify records to link

* Compare all records to all other records; 881 records means 387640 comparisons, though!
* Produce only good candidates for pairs:
  create blocks based on ZIP code.
  Only items with the same ZIP code are compared.


## Compare records

* Produce a comparison vector for each pair:
  Produces a similarity score for each field based on a similarity function defined per-field.
* Classify comparison vectors
  * Threshold-based comparison using weighted average of vector components
  * Supervised classification using training data shaped like our real data
  * There are more, but choosing a classifier may not even be the real issue.
    The blocking choice might be to blame!
    Active learning classification might be helpful: uses predicates iteratively to find best blocking choice


## Transitive closure

Given records A, B, and C, if A:B and B:C but A!:C, that doesn't make sense.
Transitive closure identifies these transitive equalities and clusters them.


## Miscellaneous

* `jellyfish` for Jaro-Winkler implementation
* `geocoder` for address geolocation
* Restaurant dataset from Fodors and Zagat restaurant guides
  Name, address, city, phone number, type, cluster
* `recordlinkage` library for record linkage

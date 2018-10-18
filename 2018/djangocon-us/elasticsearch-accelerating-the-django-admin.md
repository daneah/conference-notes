# "Elasticsearch: Accelerating the Django Admin" by Kate Kligman


## Overview

There was a small, simple customer data model, but Django was building a query to do full-text search over all fields.
This slowed down to 12 seconds by the time there were ~100Ks of records.
The decision was to use Elasticsearch to speed this up.


## Elasticsearch

### Cheat sheet

|Elasticsearch|SQL         |
|:-----------:|:----------:|
|Index        |Database    |
|Mapping      |Table schema|
|Field        |Table column|
|Document     |Table row   |


### Implementation

* Elasticsearch mappings can be brittle; things changing can mean the whole dataset is wiped out to be rebuilt.
* Uses an inverted index
* Search query -> Elasticsearch -> List of IDs matching -> rehydrate from PostgreSQL
* Since Elasticsearch is a search engine, it also performs ranked ordering


## Elasticsearch in the Django Admin

* Match the Elasticsearch ID to a column that is the primary key in the Django model
* Hook the query into the admin using `get_search_results` on the `ModelAdmin` class
* Use signals and asynchronous tasks to update Elasticsearch documents


## Libraries

* `elasticsearch-dsl-py`
* `elasticsearch-py`


## Hosting

* AWS is a managed, but limited solution. High availability is nice!


## Outcome

* &lt;1s searches across millions of records; network latency contributes most of the time spent

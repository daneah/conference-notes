# "Spark Streaming for World Domination" by Win Suen, AppNexus


## Spark
Cluster computing platform
Fast (compared to MapReduce, for instance)
Computations not calculated until they're needed (using a DAG)


## Spark Libraries
* Apache Spark (core)
* SparkSQL
* Spark Streaming
* MLlib
* GraphX


## Spark Streaming
Parallelism in data input and data processing


## Use case
Ad auctions for real-time ad impressions on the web

### Wants
* Low latency
* High and variable volume
* Fast iteration
* Scalability and reliability


## Architecture

* SparkContext
* Cluster manager
* Worker nodes
  * Executor
  * Tasks
  * Cache
* RDD (Resilient Distributed Dataset) input data
  * DStream (discretized stream) is multiple RDD sources


```python
from pyspark import SparkContext
from pyspark.streaming import StreamingContext

sc = SparkContext("local[2]", "winAwesomeApp")
ssc = StreamingContext(sc, 60)
lines = ssc.socketTextStream("localhost", 9999)

my_count = lines.count()
print(my_count)

ssc.start()
```

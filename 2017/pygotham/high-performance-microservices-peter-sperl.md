# "High Performance Microservices" by Peter Sperl, Bloomberg


## Use Case
* Structured Products Market
* Mortgage-backed securities
* Manage bonds based on consumer debt
* Billions of requests per day


## Challenges
Large variance in data size and response time
Interactive and batch users
Infrequently updated data


## Summary of Talk
* [Design for cacheability](#design-for-cacheability)
* [Immutable responses over TTL](#immutable-document-storage)
* [How you cache is as important as what you cache](#caching-approaches)
* [Turn off garbage collection](#garbage-collection)


## Design for Cacheability

Microservices are small components but each includes even more granular components (request/response lifecycle)

### TTL Caching
Allow responses to be reused within some time window
Useful for stateful services where slightly stale data is OK
Fundamental part of HTTP
Allow middlemen to cache responses
Worst-case is that users see stale data for a long time
Aim for statelessness

#### Statelessness

#### Benefits
Trivially cached
Trivially tested
Horizontally scaleable


## Immutable document storage

Database with entity ID, timestamp of change, and URI to unchanging document with data of interest
Sortable by timestamp
Database reads can be cached as well as service calls that depend on them
Batch jobs can freeze their timestamps for reading
Set max timestamp for read in event of emergency

## Caching approaches
- Cache as a service
- Local caches + shared caches

### Inter-process Communication
- TCP port exhaustion
- TCP vs. UNIX sockets (use UNIX sockets if possible!)


#### Speed tips
Use JSON or msgpack over YAML
Use lz4


## Garbage Collection
Turning off garbage collection can save response time
Certain service workers can be restarted periodically or based on consumed memory
You can request garbage collection manually (after request is served instead of during)

### Reference Cycles

Dangling objects that reference each other but nothing points to them
Use weak references to break reference cycles
Dangerous when using third-party libraries or don't realize other outside object references exist

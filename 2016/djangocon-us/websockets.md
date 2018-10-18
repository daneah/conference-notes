# Websockets
## @eusoj\_xirdneh 

### Ideas

* Requires asynchronous behavior not handled well by WSGI
* offloading helps keep threads available during long running processes
* Applications are event-based
* `django-channels`
* `asgi\_redis`

### Why Websockets?

* More robust web apps
* More complex front end interfaces
* More data processing on the servers
* HTTP request/response paradigm
* Persistent connection between client and server

### django-channels

* Django native implementation
* Malleability
* Abstract async handling
* Let other technologies tie into it

HTTP Server <-> Interface server <-> HTTP Requests/Websocket Messages <-> WebSocket consumer
                                                                      <-> HTTP consumer

#### Channels

* FIFO queue
* message expiration
* at-most-once delivery to one listener at a time
* channels have unique ID
* network transparent, accessible over the network
* capacity

* take in message, send response through message's reply channel
* groups for multiple reply channels
* `consumers.py` and `routing.py` define how consumers behave
* in-memory backend, IPC, redis

* Daphne - one interface server for all traffic (HTTP and WebSockets)
* asgi.py to get channel layer
* daphne my\_project.asgi:channel\_layer

* just need access to channel backend layer to write to the channel outside Django

# Architecting with Channels
## Andrew Godwin, Django Core Developer, Eventbrite

### Ideas

* Inspired from meteor.js
* Born from WebSockets, but expanded to be more
* A foundation for running 'async' at scale
* Targeted for Django 1.11

### The "real hard problem"

* Asynchronous coordination
    * The gap between multiple servers that need to coordinate messages

### Why?

* Streaming updates
* Chat apps
* Collab editing
* Game backends
* Broadcast

### Channels

#### Uses

* WebSockets
* Task offloading
* Chat/email integration
* IoT protocols

#### Drawbacks

* Stateful connections
* Internal network issues
* Bottlenecks

#### Options

* Send to channel X
* Receive from channel X
* Send to group Y
* Add channel X to group Y
* Remove channel X from group Y

#### Architecture

```
[ Server ]  [ Server ]  [ Django ]  [ Script ]
    |           |           |           |
[  ASGI  ]  [  ASGI  ]  [  ASGI  ]  [  ASGI  ]
    \           \          /           /
      \           \      /           /
        \          \   /           /
          \         \/            /
          [ Shared memory / redis ]
```

http://bit.ly/asgi-spec

#### Packages

* Daphne (HTTP/WebSocket server)
* Channels (Django integration)
* asgi-redis (redis backend)
* asgi-ipc (local memory backend)
* asgiref (Shared code and libraries)

#### What does Channels provide?

* Routing
* Consumers
* Sessions
* Auth
* Helpers

# "A Python-Driven Web App Framework with Django, Channels, and React" by Kendall Chuang and Henry Olson

## Channels

Channels adds a layer of asynchronicity as well as push capabilities from server to client.
This allows for long-running processes to work in the background and send results when available.


## Front-end architecture

* Application
  * Navigation
    * Pages
      * Forms
      * Blocks

Users can easily build pages using forms and blocks to get the information they want.
React, Redux, and JSONRPC methods to make WebSocket calls.

Django view serves `index.html`, then loads React application JavaScript with `staticfiles`.
`react-router` does the routing.


## Envision application flow

1. Page render
1. getPage RPC call
1. get_page Django consumer
1. getPage action
1. Reducer updates page state
1. Components rendered
1. Repeat


## WebSockets consumer

`django-channels-jsonrpc` library helps in creating RPC methods (subclassing `django-channels`' `WebSocketConsumer`)


## Investigating WebSockets traffic

Filter using the "WS" option in the Network tab in Chrome devtools

1. React app sends JSON body indicating which RPC to use
1. Channels consumer comes back with data
1. React app updates state


## State management

The channels implementation is backed by a Redis data store to keep track of the clients that need data pushed to them.
Serializing large or complex pages all at once to send through WebSockets can be tedious;
pushing partial data or a skeleton first and refreshing with real data breaks the task into digetible steps.
